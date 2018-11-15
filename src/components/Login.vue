<template>
<div class="login">
    <el-row type="flex" justify="center">
        <el-col :span="4">
            <el-row>
                <el-form :model="loginForm" ref="loginForm" label-width="0px">
                    <el-form-item prop="loginId" >
                        <el-input v-model="loginForm.loginId" placeholder="请输入ID" 
                        name='loginId' size="large">
                        </el-input>
                    </el-form-item>
                    <el-form-item prop="password">
                        <el-input v-model="loginForm.password" type="password" placeholder="请输入密码" 
                        name="password" size="large">
                        </el-input>
                    </el-form-item>
                </el-form>
            </el-row>
            <el-row>
                <el-col :span="24">
                    <el-button type="primary" :disabled="disabled" @click="handleLogin">登录</el-button>
                </el-col>
            </el-row> 
        </el-col>
    </el-row>
</div>
</template>
 
<script>
export default {
    data() {
        return {
            loginForm: {
                loginId:'',
                password:''
            },
            //disabled: true,
        } 
    },
    methods:{
        // handleChange() {
            
        // },
        handleLogin(){
            let _self = this;
            let loginId = _self.loginForm.loginId;
            let password = _self.loginForm.password;
            console.log(loginId,password);
        }
    },
    computed: {
        disabled: function() {
            let _self = this;
            if(_self.loginForm.loginId!='' && _self.loginForm.password!='') {
                return false;
            }
            else if(_self.loginForm.loginId=='' || _self.loginForm.password==''){
                return true;
            }
        }
    }
}
</script>
 
 <style scoped>
    .login {
        margin-top: 40vh;
    }
 </style>
 