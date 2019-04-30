# table-plus

### 概述

支持表格翻页


<vuep template="#example" :options="{ theme: 'mdn-like' }"></vuep>


<script v-pre type="text/x-template" id="example">
<style>
.ex-table-plus {
    margin-top: 25px;
    margin-bottom: 50px;
    width: 100%;
    position: relative;
    -webkit-box-shadow: 0 1px 2px 0 rgba(23, 35, 61, 0.35);
    box-shadow: 0 1px 2px 0 rgba(23, 35, 61, 0.35);
    max-width: 1000px;
}

</style>
<template>
    <div class='ex-table-plus'>
        <table-plus id='td-tablePlus' :options='tableOp' @on-selection-change="selectionChange">
        </table-plus>
    </div>
</template>
<script>

export default {
    data() {
        return {
            tableOp: {
                btnWords: '研究区域',
                callback: '',
                searchHolder: '搜索店铺名称',
                tips: '文件上传',
                columns: [{
                    type: 'selection',
                    width: 64,
                    align: 'center',
                    fixed: 'left',
                }, {
                    title: '区域名称',
                    key: 'name',
                    width: 302,
                    fixed: 'left',
                    //slbs-652 done
                    ellipsis: true,
                    render: (h, params) => {
                        //https://jira.tendcloud.com/browse/SLBS-719
                        const name = params.row.name;
                        if (params.row.status === "SUCCESS") {
                            return h('span', {
                                attrs: {
                                    title: name,
                                    class: 'success'
                                }
                            }, name);
                        } else {
                            return h('span', {
                                attrs: {
                                    title: name,
                                    class: 'building'
                                }
                            }, name);
                        }
                    }
                }, {
                    title: '城市',
                    key: 'city',
                    width: 140,
                    ellipsis: true,
                    render: (h, params) => {
                        const city = params.row.city
                        return h('span', {
                            attrs: {
                                title: city
                            }
                        }, city);
                    }
                }, {
                    title: '辐射范围',
                    key: 'serviceScope',
                    width: 160,
                    render: (h, params) => {
                        switch (params.row.serviceType) {
                            //1:步行，2：开车，3：圆，4：多边形
                            case 1:
                                return h('span', `步行${params.row.serviceScope}分钟`);
                            case 2:
                                return h('span', `驾车${params.row.serviceScope}分钟`);
                            case 3:
                                return h('span', `半径${params.row.serviceScope}m`);
                            case 4:
                                return h('span', '多边形区域');
                            default:
                                return h('span', params.row.serviceScope);
                        }
                    }
                }, {
                    title: '服务区域',
                    key: 'serviceArea',
                    width: 120,
                    sortable: true,
                    render: (h, params) => {
                        return h('span', params.row.serviceArea);
                    }
                }, {
                    title: '状态',
                    key: 'status',
                    width: 100,
                    //SLBS-845:研究区域列表调整
                    render: (h, params) => {
                        let result = '',
                            status = params.row.status
                        switch (status) {
                            case 'SUCCESS':
                                result = '正常'
                                break
                            case 'ERROR':
                                result = '构建失败'
                                break
                            case 'BUILDING':
                                result = '构建中'
                                break
                            default:
                                result = ''
                                break
                        }
                        return h('span', result)
                    }
                }, {
                    title: ' ',
                    key: 'action',
                    // width: 66,
                    align: 'center',
                    render: (h, params) => {
                        return h('div', [
                            h('a', {
                                'class': {
                                    'icon-delete': true
                                },
                                style: {
                                    border: 'none',
                                    pointer: 'cursor',
                                    fontSize: '20px',
                                    visibility: 'hidden'
                                },
                                on: {
                                    click: () => {
                                        if (this.$utils.accountDemo()) {
                                            this.$Message.error({
                                                content: 'Demo数据，无法操作',
                                                maxCount: 1
                                            });
                                            return;
                                        }
                                        //调用接口deleteIntentionStore，删除意向门店
                                        this.deleteIntentionShop(params);
                                    }
                                }
                            }, '')
                        ]);
                    }
                }],
                data: [],
                isDelete: true,
            },
            pageList: [{ "serviceType": 3, "score": 44.0, "lng": "116.643422281780261", "polygon": null, "serviceArea": 125600.0, "city": "北京市", "brandId": 240, "name": "麦当劳(迎宾中路餐厅)", "serviceScope": 200, "id": 2290, "lat": "40.321470735564624", "status": "SUCCESS" }]
        }
    },
    mounted() {
        this.tableOp.data = this.pageList;
    },
    methods: {
        selectionChange(value) {
            // this.deleteList = value;
            console.log(value)
        },
    }
}

</script>


</script>



### API

### Attributes

| 属性        | 说明   |  类型  |  默认值 |
| --------   | -----:  | :----:  | :----:  |
| options    | 表格数据，见iview table格式 |   Object    |   {}    |


### Methods

| 事件名        | 说明   |  返回值  |
| --------   | -----:  | :----:  |
| on-selection-change    | 勾选触发 |   选中的数组对象    |