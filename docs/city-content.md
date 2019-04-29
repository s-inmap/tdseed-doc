# city-content

### 概述

支持下拉选择城市


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div id="ex-filter-city">
        <div class="position">
            <Poptip placement="bottom-end" width="220" v-model="visible" @on-popper-show="onPopperShow">
                <div class="cityPop hoverPop">
                    <i class="icon-funnel"></i>选择城市
                </div>
                <div class="api" slot="content">
                    <city-content v-model="checkCity" :data="selectCityData" @on-change="cityChange" @on-submit="submitCity" @on-cancel@on-cancel="cancelCity"></city-content>
                </div>
            </Poptip>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            visible: false,
            checkCity: [],
            selectCityData: [],
            pageList: [{ "serviceType": 3, "score": 44.0, "lng": "116.643422281780261", "polygon": null, "serviceArea": 125600.0, "city": "北京市", "brandId": 240, "name": "麦当劳(迎宾中路餐厅)", "serviceScope": 200, "id": 2290, "lat": "40.321470735564624", "status": "SUCCESS" }]
        }
    },
    methods: {
        onPopperShow() {
            this.selectCityData.push(this.pageList);
        },
        cityChange(value) {
            this.checkCity = value;
            console.log(value)
        },
        submitCity(value) {
            this.visible = false;
        },
        cancelCity(value) {
            this.visible = false;
            console.log(value)
        }
    }
}

</script>
<style>
#ex-filter-city {
    position: relative;
    .position {
        position: absolute;
        top: 0;
        left: 0;
        .cityPop {
            line-height: 32px;
            width: 104px;
            cursor: pointer;
            text-align: center;
            font-size: 14px;
            color: var(--color-hover);
        }
        .ivu-poptip-body {
            padding: 0;
        }
        .ivu-poptip-body-content {
            overflow: hidden;
        }
    }
}

</style>


</script>
</script>

### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| v-model    | 城市数据 |   Array    |   []    |
| data    | 禁用 |   Boolean    |   false    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-change    | 勾选，取消勾选时触发 |   选中城市数组    |
| on-submit    | 更新时触发 |   数组    |
| on-cancel    | 取消时触发 |   数组    |