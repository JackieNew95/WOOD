<template>
    <div class="panel admin-panel">
        <div class="panel-head" id="add"><strong><span class="icon-pencil-square-o"></span>更新栏目</strong></div>
        <div class="body-content">
            <el-form ref="form" :model="form" label-width="80px">
                <el-form-item label="ID:">
                    {{form.cid}}
                </el-form-item>
                <el-form-item label="栏目名称:">
                    <el-input v-model="form.cname"></el-input>

                </el-form-item>
                <el-form-item label="父栏目:">
                    <el-select style="float: left" v-model="form.pid" clearable placeholder="请选择">
                        <el-option
                                v-for="item in options"
                                :key="item.value"
                                :label="item.cname"
                                :value="item.cname">
                        </el-option>
                    </el-select>
                </el-form-item>
                <el-form-item>
                    <el-button type="primary" @click="handleSubmit('form')">立即提交</el-button>
                </el-form-item>
            </el-form>
        </div>
    </div>
</template>
<script>
    export default {
        name:'updateCategory',
        data(){
            return{
                form:{
                    cid:'',
                    cname:'',
                    pid:'',
                },
                options:[],
            }
        },
        mounted(){
            this.form.cid=this.$route.query.id;
            this.form.cname=this.$route.query.cname;
            this.form.pid=this.$route.query.pid;
            this.$http.get('/wood/query.php?table=category').then(res=>{
                this.options=res.body;
            })
        },
    }
</script>
<style>
    @import "../../../assets/css/admin.css";
    @import "../../../assets/css/pintuer.css";
</style>