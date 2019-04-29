# filter-city

### 概述

支持过滤城市


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div id="ex-filter-city">
        <filter-city :data="pageList" @on-change="onChange" @on-submit="onSubmit" @on-cancel="onCancel" @on-popper-show="onPopperShow"></filter-city>
    </div>
</template>
<script>
export default {
    data() {
        return {
            pageList: [{ "serviceType": 3, "score": 44.0, "lng": "116.643422281780261", "polygon": null, "serviceArea": 125600.0, "city": "北京市", "brandId": 240, "name": "麦当劳(迎宾中路餐厅)", "serviceScope": 200, "id": 2290, "lat": "40.321470735564624", "status": "SUCCESS" }]
        }
    },
    methods: {
        onPopperShow() {},
        onChange(value) {
            console.log(value)
        },
        onSubmit(value) {
            console.log(value)
        },
        onCancel(value) {
            console.log(value)
        }
    }
}

</script>
<style>
#ex-filter-city {
    position:relative;
    width: 200px;
    height: 200px;
}

</style>


</script>

### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| data    | 城市数据 |   Array    |   []    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-change    | 勾选，取消勾选时触发 |   选中城市数组    |
| on-submit    | 更新时触发 |   数组    |
| on-cancel    | 取消时触发 |   数组    |
| on-popper-show    | pop打开时触发 |   选中的数组    |