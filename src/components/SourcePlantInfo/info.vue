<template>
    <div>
        <Table border :columns="columns" :data="data"></Table>
    </div>
</template>
<script>
import axios from 'axios'
    export default {
        data () {
            return {
                modal: false,
                columns: [
                    {
                        title: '产生源序号',
                        key: 'sourceId',
                        sortable: true
                    },
                    {
                        title: '产生源位置',
                        key: 'sourceAddress'
                    },
                    {
                        title: '上报时间',
                        key: 'startDate'
                    },
                    {
                        title: '属性',
                        key: 'sourceAttrbute'
                    },
                    {
                        title: '责任单位',
                        key: 'sourceCompany'
                    },
                    {
                        title: '产生垃圾类型',
                        key: 'sourceType'
                    },
                    {
                        title: '成分分析',
                        key: 'wasteComponent'
                    },
                    {
                        title: '结束时间',
                        key: 'endDate'
                    },
                    {
                        title: '垃圾总量',
                        key: 'wasteTotal',
                        sortable: true
                    },
                    {
                        title: '总量单位',
                        key: 'wasteUnit',
                    },
                    {
                        title: '处置建议',
                        key: 'suggestion'
                    },
                    {
                        title: '录入人名称',
                        key: 'inputName'
                    },
                    {
                        title: '录入时间',
                        key: 'inputTime'
                    },
                    {
                        title: '备注',
                        key: 'content'
                    }
                ],
                data: []
            }
        },

        created () {
             axios({
                headers: {
                  token: this.$store.state.token
                },
                method: "get",
                url:'/api/sourceInfo/si'
                })
                .then(response => (this.data = response.data))
                .catch(error => console.log(error))
        },

  
       
    }
</script>
