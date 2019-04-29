# basic-bar

### 概述

支持条状


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-basic-bar'>
        <h1>basic-bar</h1>
        <basic-bar :value="0"></basic-bar>
        <br>
        <basic-bar :value="20.6"></basic-bar>
        <br>
        <basic-bar :value="50.6"></basic-bar>
        <br>
        <basic-bar :value="70.6"></basic-bar>
        <br>
        <h1>mini-bar</h1>
        <basic-bar :value="36.5" size="mini"></basic-bar>
    </div>
</template>
<script>
export default {
    data() {
        return {}
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
.ex-basic-bar {
    width: 200px;
    .td-basic-bar {
        margin-bottom: 10px;
    }
}

</style>


</script>


### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| value    | 百分比值 |   Number    |   0    |
| size    | 类型:''\|'mini' |   String    |   ''    |

