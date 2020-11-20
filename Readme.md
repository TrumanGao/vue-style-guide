# 前端代码规范 - Vue规范

## 一、页面 / 模块规范
1. 模块以业务划分，每个业务模块放置在独立文件夹，以 1-2 个单词精简命名
2. kabebCase 格式（驼峰式命名），首字母大写
3. 模块内如有一级页面 / 核心业务页面，与模块同名
4. 模块内其他页面，以模块名开头，以具体业务名称结尾
```js
src
  -- views
    -- Home
      -- Home.vue
    -- Library
      -- Library.vue
      -- LibraryDetail.vue
    -- User
      -- UserDetail.vue
      -- UserContacts.vue
```

## 二、组件规范
1. 组件名为多个单词，以避免与现有和未来的 HTML 元素冲突
2. pascal-case 格式（短横线连接），全部小写
3. 模块内的组件：统一放置在模块内独立的 components 文件夹
- 3.1 以所在模块名称前缀，以功能命名
``` js
views
  -- Library
    -- Library.vue
    -- components
      -- library-upload.veu
      -- library-breadcrubm.vue
  -- User
    -- components
      -- user-info-form.vue
```
4. 全局组件：统一放置在根目录下的 components 文件夹
- 4.1 基础组件：应用特定样式和约定，展示类的、无逻辑的或无状态的组件，以 base 前缀，以功能命名
- 4.2 单例组件：只应该拥有单个活跃实例的组件，以 the 前缀，以功能命名
```js
src
  -- components
    -- base-button.vue
    -- base-input.vue
    -- the-login.vue
```
**注意：如两个以上模块复用，即抽离为全局组件** 

## 三、接口文件规范
1. 接口文件统一置于根目录下 api 文件夹
2. 封装 request.js / http.js 文件处理网络请求配置
3. 接口封装以业务类型划分
3. 接口文件命名以 api 开头，以业务类型结尾
```js
src
  -- api
    -- request.js
    -- apiAccount.js
    -- apiGoods.js
    -- apiLibrary.js
```

## 其他资源规范
1. 图片资源
如果本地图片资源较多，按照模块放置在独立文件夹。文件夹命名与模块保持一致
```js
src
  -- assets
    -- img
      -- Home
        -- logo.png
        -- background.png
      -- User
        -- defaultAvatar.png
```

## 四、样式（css / sass / less）规范
1. 组件样式加上作用域 scoped，防止样式污染
2. 如果使用css预编译语言，子节点样式代码包裹在父节点样式代码内，防止样式污染
3. 页面根节点样式类，以 页面文件名称命名，以 page 后缀
```js
// Library.vue
<template>
    <div class="library-page">
    </div>
</template>
...
<style scoped>
.library-page{}
<style>
```
4. 组件根节点样式类，与组件名称同名
```js
// the-login.vue
<template>
    <div class="the-login">
    </div>
</template>
...
<style scoped>
.the-login{}
<style>
```
4. 全局样式文件放置在 静态资源文件夹下 style 文件夹内
```js
src
  -- assets
    -- img
      -- User
        -- defaultAvatar.png
    -- style
      -- global.css
      -- elementUI.css
```

## 扩展阅读
[风格指南 — Vue.js](https://cn.vuejs.org/v2/style-guide/)