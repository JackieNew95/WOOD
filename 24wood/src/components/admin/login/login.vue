<template>
    <div class="login">
        <div class="bg"></div>
        <div class="container">
            <div class="line bouncein">
                <div class="xs6 xm4 xs3-move xm4-move">
                    <div style="height:150px;"></div>
                    <div class="media media-y margin-big-bottom">
                    </div>
                   <el-form ref="form" :rules="rules" :model="form" label-width="80px">
                        <div class="panel loginbox">
                            <div class="text-center margin-big padding-big-top"><h1>后台管理中心</h1></div>
                            <div class="panel-body" style="padding:30px; padding-top:10px;">
                                <div class="field field-icon-right">
                                    <el-form-item label="用户名：" prop="user">
                                        <el-input v-model="form.user" ></el-input>
                                        <span class="icon icon-user margin-small"></span>
                                    </el-form-item>
                                </div>
                                <div class="field field-icon-right">
                                    <el-form-item label="密码：" prop="pass">
                                        <el-input type="password" v-model="form.pass" auto-complete="off"></el-input>
                                        <span class="icon icon-key margin-small"></span>
                                    </el-form-item>
                                </div>
                                <el-form-item label="验证码：" prop="code">
                                    <el-input style="width: 50%" v-model="form.code"></el-input>
                                    <img :src="src" alt="" @click="src='/wood/code.php?id='+Math.random()">
                                </el-form-item>
                                <el-button type="primary" @click="onSubmit('form')" class="button button-block bg-main text-big input-big">登录</el-button>
                            </div>
                        </div>
                    </el-form>
                </div>
            </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: 'login',
        data() {
            return {
                src:'/wood/code.php',
                form: {
                    user: '',
                    pass: '',
                    code: '',
                },
                rules: {
                    user: [
                        {required: true, message: '请输入用户名', trigger: 'blur'},
                        {min: 2, max: 8, message: '长度在 2 到 8 个字符', trigger: 'blur'}
                    ],
                    pass: [
                        {required: true, message: '请输入密码', trigger: 'blur'},
                        {min: 3, max: 8, message: '长度在 3 到 8 个字符', trigger: 'blur'}
                    ],
                    code: [
                        {required: true, message: '请输入验证码', trigger: 'blur'}
                    ],
                }
            }
        },
        methods: {
            onSubmit(formName) {
                this.$refs[formName].validate((valid) => {
                    if (valid) {
                        this.$http.post('/wood/checkLogin.php', this.form).then(res => {
                            if (res.body=='ok') {///成功之后的返回值1，或者每一行的数据
                                this.$message({
                                    message: '恭喜你，登录成功',
                                    type: 'success'
                                });
                                ////编程式跳转页面,()里面是路由规则里面的名称
                                this.$router.push('main');
                            } else if (res.body=='error') {
                                this.$message.error('请检查你的密码和验证码');
                            }
                        })///跨域发送数据
                    } else {
                        console.log('error submit!!');
                        return false;
                    }
                })
            },
        },
    }
</script>
<style>
    @import "../../../assets/css/admin.css";
    @import "../../../assets/css/pintuer.css";
</style>