# map-modal

### 概述

支持地图弹出框

<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div id="ex-map-modal">
        <i-button @click="open" class="">打开弹出框</i-button>
        <map-modal v-model="isShow" :data="editItem" :map="this.map" :validateData="names" @on-cancel="handleCancel" @on-submit="handleSubmit"></map-modal>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isShow: false,
            editItem: {
                id: 152,
                userId: 10019,
                name: '天使之橙',
                poiid: [],
                event: {
                    clientX: 0,
                    clientY: 0
                }
            },
            names: [{
                name: '天使之橙'
            }],
            map: null
        }
    },
    created() {

    },
    methods: {
        open(e) {
            this.editItem.event.clientX = e.clientX;
            this.editItem.event.clientY = e.clientY;

            this.isShow = true;
        },
        handleCancel(val) {
            console.log(val);
            this.isShow = false;
        },
        handleSubmit(val) {
            console.log(val);
            this.isShow = false;
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
| v-model    | 弹出框显示隐藏 |   Array    |   []    |
| data    | 编辑研究区域的对象 |   Object    |   {}    |
| map    | 百度地图实例 |   Object    |   {}    |
| validateData    | 已重名的数组，会报错('名称已存在') |   Array    |   []    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-submit    | 提交时触发 |   编辑的对象    |
| on-cancel    | 取消时触发 |       |