# seed

> A city map with components library by Vue2.0.js

## 文档
https://s-inmap.github.io/tdseed-doc/#/


## CDN 引入
``` script
<link rel="stylesheet" href="https://unpkg.com/tdseed/dist/static/tdseed.css">
<script src="https://unpkg.com/vue@2.5.17/dist/vue.js"></script>
<script src="https://unpkg.com/iview@2.14.3/dist/iview.min.js"></script>
<script src="https://unpkg.com/lodash@4.17.11/lodash.js"></script>
<script type="text/javascript" src="https://unpkg.com/tdseed/dist/tdseed.min.js"></script>
```

## NPM 安装
``` bash
$ npm install tdseed --save
```


### 示例

``` html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
    <title>tdseed example</title>
    <link rel="stylesheet" href="https://unpkg.com/tdseed/dist/static/tdseed.css">
    <script src="https://unpkg.com/vue@2.5.17/dist/vue.min.js"></script>
    <script src="https://unpkg.com/iview@2.14.3/dist/iview.min.js"></script>
    <script src="https://unpkg.com/lodash@4.17.11/lodash.js"></script>
    <script type="text/javascript" src="https://unpkg.com/tdseed/dist/tdseed.min.js"></script>
</head>

<body>
    <div id="app">
        <div style="width: 336px;">
            <i-button @click="show">Click me!</i-button>
            <mul-chooser v-model="indexs" :data="this.officeListState" :disable="false" @on-change="_onChooserChange"></mul-chooser>
        </div>
    </div>
</body>
<script>
new Vue({
    el: '#app',
    data: {
        indexs: [],
        officeListState: [{
            "id": 1,
            "city": "北京市",
            "name": "怀柔区"
        }, {
            "id": 2,
            "city": "北京市",
            "name": "平谷区"
        }, {
            "id": 3,
            "city": "北京市",
            "name": "昌平区"
        }, {
            "id": 4,
            "city": "北京市",
            "name": "大兴区"
        }, {
            "id": 5,
            "city": "北京市",
            "name": "通州区"
        }, {
            "id": 6,
            "city": "北京市",
            "name": "顺义区"
        }, {
            "id": 7,
            "city": "北京市",
            "name": "房山区"
        }, {
            "id": 8,
            "city": "北京市",
            "name": "朝阳区"
        }, {
            "id": 9,
            "city": "北京市",
            "name": "丰台区"
        }, {
            "id": 10,
            "city": "北京市",
            "name": "东城区"
        }, {
            "id": 11,
            "city": "北京市",
            "name": "西城区"
        }, {
            "id": 12,
            "city": "北京市",
            "name": "门头沟区"
        }, {
            "id": 13,
            "city": "北京市",
            "name": "石景山区"
        }, {
            "id": 14,
            "city": "北京市",
            "name": "海淀区"
        }, {
            "id": 16,
            "city": "北京市",
            "name": "密云区"
        }, {
            "id": 17,
            "city": "北京市",
            "name": "延庆区"
        }]
    },
    mounted() {},
    methods: {
        show: function() {
            console.log(1)
        },
        _onChooserChange(result) {
            console.log(result)
        }
    }
})
</script>

</html>
```


