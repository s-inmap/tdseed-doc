# map-modal

### 概述

支持地图弹出框

<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div id="ex-map-modal">
        <Button @click="open" class="">打开弹出框</Button>
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
| data    | 城市数据 |   Array    |   []    |
| disable    | 禁用 |   Boolean    |   false    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-change    | 更改选中项时触发 |   选中的数组    |