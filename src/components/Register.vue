<template>
    <div class="register container text-center mt-5">
        <img src="../../static/logo.png" width="100" alt="">
        <h3>注册</h3>
        <form>
            <div class="form-group">
                <input type="email" class="form-control" id="input1" v-model="username" placeholder="请输入您的邮箱...">
            </div>
            <div class="form-group">
                <input type="password" class="form-control" id="input1" v-model="username" placeholder="请输入您的密码...">
            </div>
            <div class="form-group">
                <input type="repassword" class="form-control" id="input1" v-model="username" placeholder="请再次确认您的密码...">
            </div>
            <div class="form-check">
                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                <label for="exampleCheck1" class="form-check-label">Rember me</label>
            </div>
            <button type="submit" @click.prevent="onSubmit" class="btn btn-primary btn-block">注册</button>
        </form>

    </div>
</template>

<script>
import axios from 'axios';

export default {
    name:'Register',
    data(){
        return{
            username:'',
            password:'',
            repassword:''
        }
    },
    methods:{
        onSubmit(){
            //非空验证
            if(this.password==''&&this.username==''){
                return
            }
            //进行当前密码的重复确认
            if(this.password===this.repassword){
                var formData={
                    username:this.username,
                    password:this.password
                }
                axios.post('./user-jfc.json',formData)
                .then(res=>{
                    this.$router.replace('/login')
                })
            }
        }
    }
}
</script>

<style>
.form-control{
    width: 500px;
}
.register{
    width: 500px;
    margin: 0 auto;
}
.btn-block{
    width:107%;
}
</style>

