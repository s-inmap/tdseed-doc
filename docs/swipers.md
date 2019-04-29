# swipers

### 概述

支持滑动


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-swipers-plus'>
        <button @click="one">one</button>
        <button @click="two">two</button>
        <button @click="three">three</button>
        <Swipers ref="swipers" id="Swipers">
            <div slot="nav" class="top">
                <h1>文章标题</h1>
            </div>
            <SwiperPane name="mainPage" animation="slide-in">
                <div>one</div>
            </SwiperPane>
            <SwiperPane name="filterPage" animation="slide-out">
                <div>two</div>
            </SwiperPane>
            <SwiperPane name="resultPage" animation="slide-in">
                <div>three</div>
            </SwiperPane>
        </Swipers>
    </div>
</template>
<script>
export default {
    data() {
        return {}
    },
    mounted() {},
    methods: {
        one() {
            this.$refs.swipers.open('mainPage')
        },
        two() {
            this.$refs.swipers.open('filterPage')
        },
        three() {
            this.$refs.swipers.open('resultPage')
        }
    }
}

</script>
<style>
.ex-swipers-plus {
    #Swipers {
        position: relative;
    }
}

</style>


</script>


### API

### Swiper Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| loading    | 是否显示loading |   Boolean    |   false    |


### SwiperPane Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| name    | 命名 |   String    |   ''    |
| animation    | 动效'slide-in' \| 'slide-out' |   String    |   'slide-in'    |

### slot

| 名称        | 说明   |
| --------   | -----:  |
| nav    | 自定义页头 |

### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| open(name)    |  this.$refs.swipers.open('page'),打开某一命名页 |       |