# bar-table

### 概述

支持排行

<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-bar-table'>
        <bar-table title="学历|当前区域|全国|TGI" :data="purchasePower" :loading="loading" :colors="color"></bar-table>
    </div>
</template>
<script>
export default {
    data() {
        return {
            color: ['#34508C', '#2B85E4', '#1CB6FB', '#1BDBF5', '#80F2DA', '#C1F9D6'],
            loading: false,
            purchasePower: [{
                    "key": "土豪",
                    "value": 3.94
                },
                {
                    "key": "高级白领",
                    "value": 66.97
                },
                {
                    "key": "小白领",
                    "value": 27.04
                },
                {
                    "key": "蓝领",
                    "value": 2.01
                },
                {
                    "key": "收入很少",
                    "value": 0.04
                },
                {
                    "key": "未知",
                    "value": 0
                }
            ]
        }
    },
    created() {},
    mounted() {

    },
    methods: {
    }
}

</script>

<style>
.ex-bar-table {
    width: 400px;
    /*.td-bar-table .main .column .info {
        .col-1 {
            border: 0;
        }
        .col-2,
        .col-3 {
            display: none;
        }
    }*/
}

</style>


</script>

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