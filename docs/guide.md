# 快速上手

## 引入 tdseed
你可以引入整个 tdseed。

在 main.js 中写入以下内容：
``` js
import Vue from 'vue';
import App from './App.vue';
import iView from 'iview';
import tdseed from 'tdseed'
import 'iview/dist/styles/iview.css';
import 'tdseed/dist/static/tdseed.css';

Vue.use(iView);
Vue.use(tdseed);

new Vue({
  el: '#app',
  components: { App },
  render: h => h(App)
});
```
以上代码便完成了 tdseed 的引入。需要注意的是，样式文件需要单独引入。