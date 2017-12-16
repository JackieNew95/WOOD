<template>
    <div class="panel admin-panel">
        <div class="panel-head"><strong class="icon-reorder">栏目列表</strong></div>
        <div class="padding border-bottom">
            <router-link class="button border-yellow" :to="{name:'addClasses'}">
                <span class="icon-plus-square-o"></span> 添加栏目</router-link>
        </div>
        <el-table
                :data="tableData"
                style="width: 100%">
            <el-table-column
                    prop="cid"
                    label="ID">
            </el-table-column>
            <el-table-column
                    prop="cname"
                    label="栏目名称">
            </el-table-column>
            <el-table-column
                    prop="pid"
                    label="父栏目">
            </el-table-column>
            <el-table-column label="操作">
                <template slot-scope="scope">
                    <el-button
                            size="mini"
                            @click="handleEdit(scope.row)">编辑</el-button>
                    <!--<router-link :to="{name:'updateDir',query:{id:scope.row.did,dname:scope.row.dname}}">编辑</router-link>-->
                    <el-button
                            size="mini"
                            type="danger"
                            @click="handleDelete(scope.row.cid)">删除</el-button>
                    <!--scope.row表示每一行的信息-->
                </template>
            </el-table-column>
        </el-table>
    </div>
</template>
<script>
    export default {
        name:'category',
        data(){
            return{
                tableData:[],
            }
        },
        mounted(){
            this.$http.get('/wood/query.php?table=category').then(res=>{
                this.tableData=res.body;
            })
        },
        methods:{
            handleEdit(item){
                this.$router.push({name:'updateCategory',query:{id:item.cid,cname:item.cname,pid:item.pid}});
            }

        }
    }
</script>
<style>
    @import "../../../assets/css/admin.css";
    @import "../../../assets/css/pintuer.css";
</style>