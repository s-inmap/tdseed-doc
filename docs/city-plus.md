# city-plus

### 概述

支持城市列表，选择城市


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div id="ex-city-plus">
        <city-plus :data="cityArray" :allowedCity="allowedCity" @on-change="onSelect"></city-plus>
    </div>
</template>
<script>
import cityList from '../data/cityList'

export default {
    data() {
        return {
            cityArray: [],
            allowedCity: ["深圳市", "无锡市", "西安市", "东莞市", "南昌市", "北京市", "中山市", "上海市", "乌鲁木齐市", "佛山市", "保定市", "兰州市", "南京市", "嘉兴市", "南宁市", "南通市", "厦门市", "台州市", "合肥市", "哈尔滨市", "大连市", "天津市", "太原市", "宁波市", "常州市", "广州市", "徐州市", "杭州市", "武汉市", "沈阳市", "泉州市", "济南市", "温州市", "潍坊市", "烟台市", "珠海市", "石家庄市", "福州市", "绍兴市", "苏州市", "贵阳市", "郑州市", "重庆市", "金华市", "镇江市", "长春市", "长沙市", "青岛市", "成都市", "惠州市", "昆明市", "晋中市"]
        }
    },
    created() {

    },
    mounted() {
        //获取到键值对数组
        let array = Object.entries(cityList);
        this.cityArray = array.filter((item) => {
            return item[0] !== 'fcList';
        });
    },
    methods: {
        onSelect(val) {
            console.log(val)
        }
    }
}

</script>
<style>


</style>


</script>


### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| data    | 城市数据 |   Array    |   []    |
| disable    | 禁用 |   Boolean    |   false    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-change    | 更改选中项时触发 |   选中的数组    |