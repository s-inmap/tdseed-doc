# top-rank

### 概述

支持排名


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-top-rank'>
        <top-rank :data="data" :loading="loading"></top-rank>
    </div>
</template>
<script>
export default {
    data() {
        return {
            data: [{
                    "key": "手机app",
                    "value": 93.05
                },
                {
                    "key": "Pc端",
                    "value": 3.54
                },
                {
                    "key": "微信",
                    "value": 1.27
                },
                {
                    "key": "手机qq",
                    "value": 0
                },
                {
                    "key": "其他",
                    "value": 0.64
                },
                {
                    "key": "未知",
                    "value": 1.51
                }
            ],
            loading: false
        }
    },
    created() {},
    mounted() {

    },
    methods: {

    }
}

</script>
<style scoped>


</style>
<style>
.ex-top-rank {
    width: 400px;
}

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