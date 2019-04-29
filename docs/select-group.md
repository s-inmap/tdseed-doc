# select-group

### 概述

支持多条件筛选


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
    <div class='ex-select-group'>
        <div v-if="visible">
             <Button type="primary" class="add" style="width:134px" @click="addCondition">
                <Icon type="plus-round"></Icon>添加筛选条件
            </Button>
            <Button type="primary" class="add" style="width:134px" @click="edit">
                <Icon type="plus-round"></Icon>编辑
            </Button>
        </div>
        <select-group ref="selectGroup" v-model="modelData" :data="conditionData" @on-minus="onMinus"></select-group>
        <Button type="primary" class="submit" :class="{disabled:visible}" @click="submit">开始筛选</Button>
        <a href="javascript:void(0)" v-if='!visible' class="clear" @click="clearConditions">清空条件</a>
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
        async mergeObject() {
            try {
                let res = await this.getRecommendListPromise();

                let data = res.data.data || [];

                data.unshift({
                    'key': '距离',
                });
                let res1 = await this.getClassification();
                let data1 = res1.data.data || [];

                this.conditionData = Object.assign({}, {
                    custom: data,
                    installation: data1
                });
                console.log('例子', this.conditionData)
            } catch (e) {
                // statements
                console.log(e);
            }

        },
        getClassification() {
            //获取poi分类
            let origin = location.origin;
            let url = origin + '/static/classification.json';

            let config = {
                method: 'get',
                url: url
            }

            return this.$axios(config);
        },
        async addCondition() {
            let res = await this.getRecommendListPromise();
            let list = res.data.data || [];
            this.recList = list;
            this.$refs['selectGroup'].addGroup();
            this.visible = false;
            this.$emit('on-condition');

            this.mergeObject();
        },
        edit() {
            // this.$refs['selectGroup'].addGroup();
            this.visible = false;
            this.mergeObject();
            this.modelData = {
                brandId: 294,
                createTime: null,
                id: 3,
                name: "fdfs",
                // params: '{"brandId":294,"name":"fdfs","recommendationId":null,"city":"北京市","groupRelation":"and","conditionGroups":[{"relation":"","conditions":[{"classification":"poi","type":"汽车服务,洗车场","distance":100,"num":0,"numCompareSymbol":">","customParam":"","customValue":null,"customSymbol":""}]}]}',

                // '{"brandId":294,"name":"fdfs","recommendationId":null,"city":"北京市","groupRelation":"and","conditionGroups":[{"relation":"","conditions":[{"classification":"poi","type":"汽车服务,洗车场","distance":300,"num":0,"numCompareSymbol":"<","customParam":"","customValue":300,"customSymbol":""},{"classification":"store","type":"","distance":300,"num":0,"numCompareSymbol":"<","customParam":"","customValue":300,"customSymbol":""}]}]}'

                // '{"brandId":294,"name":"fdfs","recommendationId":null,"city":"北京市","groupRelation":"and","conditionGroups":[{"relation":"","conditions":[{"classification":"poi","type":"汽车服务,洗车场","distance":300,"num":0,"numCompareSymbol":"<","customParam":"","customValue":300,"customSymbol":""},{"classification":"store","type":"","distance":300,"num":0,"numCompareSymbol":"<","customParam":"","customValue":300,"customSymbol":""},{"classification":"store","type":"","distance":300,"num":0,"numCompareSymbol":"<","customParam":"","customValue":300,"customSymbol":""}]}]}'
                params: '{"brandId":264,"name":"eee","recommendationId":null,"city":"北京市","groupRelation":"and","conditionGroups":[{"relation":"","conditions":[{"classification":"poi","type":"汽车服务,洗车场","distance":100,"num":0,"numCompareSymbol":">","customParam":"","customValue":null,"customSymbol":""}]}]}',
                result: null,
                status: "SUCCESS",
                userId: 10019
            }
        },
        getRecommendListPromise() {
            //获取某用户的推荐任务列表
            let origin = location.origin;
            let url = origin + '/static/tasklist.json';

            let config = {
                method: 'get',
                url: url
            }
            return this.$axios(config);
        },
        onMinus(x) {
            console.log(x)
            if (x) {
                this.visible = true;
            }
        },
        submit() {
            let obj = this.$refs['selectGroup'].validate();
            console.log(obj)
        },
        clearConditions() {
            this.visible = true;
            this.recValue = '';
            this.$refs['selectGroup'].clear();
            this.$emit('on-clear');
        },
    }
}

</script>
<style scoped>


</style>
<style>
.ex-select-group {
    width: 672px;
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