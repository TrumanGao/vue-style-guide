# 前端代码规范

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
      -- components
        -- library-group-item.vue
    -- User
      -- UserDetail.vue
      -- UserContacts.vue
```

## 二、组件规范

### 组件命名

1. 组件名为多个单词，以避免与现有和未来的 HTML 元素冲突
2. pascal-case 格式（短横线连接）
3. 模块内的组件：以所在模块名称开头，以 item 结尾
``` js
Library
  -- components
    -- library-group-item.vue
    -- library-upload-item.veu
    -- library-breadcrubm-item.vue
```
4. 全局组件：以功能命名，以 item 结尾
```js
src
  -- components
    -- login-item.vue
    -- showlist-item.vue
```

### 组件路径
1. 模块内的组件
```js
src/views/模块名称/components/  
```
![views](/img/views.jpg)

2. 全局组件  
- 2.1 自动注册的全局基础组件，放置在 components / Base 文件夹内，命名以 base 开头
```js
src
  -- components
    -- login-item.vue
    -- Base
      -- base-button-item.vue
      -- base-textarea-item.vue
```
**注意：如两个以上模块复用，即抽离为全局组件**      
![components](/img/components.jpg)

## 三、接口文件规范
1. 接口文件统一置于根目录下 api 文件夹
2. request.js 文件处理网络请求配置
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
![api](/img/api.jpg)

## 其他资源规范
1. 图片资源
如果本地图片资源较多，按照模块放置在独立文件夹。文件夹命名与模块保持一致        
![img](/img/img.jpg)

## 四、样式（css / sass / less）规范
1. 组件样式加上作用域 scoped，防止样式污染
2. 如果使用css预编译语言，子节点样式代码包裹在父节点样式代码内，防止样式污染
3. 页面根节点样式类，以 文件名称开头，以 page 结尾
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

4. 组件根节点样式类，以组件名称命名
```js
// login-item.vue
<template>
    <div class="login-item">
    </div>
</template>
...
<style scoped>
.login-item{}
<style>
```