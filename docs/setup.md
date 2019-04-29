# 安装

## npm 安装
推荐使用 npm 的方式安装，它能更好地和 webpack 打包工具配合使用。
``` bash
npm i tdseed -S
```

## UMD

index.html

``` bash
<!-- 引入样式 -->
<link rel="stylesheet" href="https://unpkg.com/iview@2.14.3/dist/styles/iview.css">
<link rel="stylesheet" href="https://unpkg.com/tdseed/dist/static/tdseed.css">
<!-- 引入组件库 -->
<script src="https://unpkg.com/lodash/lodash.min.js"></script>
<script src="https://unpkg.com/iview@2.14.3/dist/iview.min.js"></script>
<script src="https://unpkg.com/tdseed/dist/tdseed.min.js"></script>
```
目前可以通过 unpkg.com/tdseed 获取到最新版本的资源，在页面上引入 js 和 css 文件即可开始使用。