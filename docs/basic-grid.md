# basic-grid

### 概述

支持标题内容框样式


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-basic-grid'>
        <basic-grid title="标题">
            <div>内容</div>
        </basic-grid>
    </div>
</template>
<script>
import utils from '@/lib/utils';
import classification from '../data/classification';
export default {
    data() {
        return {
            visible: true,
            conditionData: {},
            modelData: {}
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
.ex-basic-grid {
    width: 400px;
}

</style>


</script>


### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| title    | 标题 |   String    |   ''    |


### slot

| 名称        | 说明   |
| --------   | -----:  |
| header    | 自定义页头 |
