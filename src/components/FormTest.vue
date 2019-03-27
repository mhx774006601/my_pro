<template>
    <div>
        <!-- 自构建的表单1 -->
        
        {{rullForm}}

        <m-form :model="rullForm" :rules='rules' ref="loginForm2">
             <m-form-item label='用户名' prop='name'>
                <m-input v-model="rullForm.name"></m-input>
            </m-form-item>
            <m-form-item label='密码' prop='pwd'>
                <m-input v-model="rullForm.pwd" type='password'></m-input>
            </m-form-item>
            <m-form-item>
                <button @click="submitForm2">登录</button>
            </m-form-item>
        </m-form>
       
    </div>
</template>

<script>
import MInput from './Input'
import MFormItem from './FormItem'
import MForm from './Form'
    export default {
        data() {
            return {
                someValue: 'some value',
                rullForm: {
                    name: '',
                    pwd: ''
                },
                rules:{
                    name:[{required: true, message: '请输入用户名', trigger: 'blur'}],
                    pwd:[{required: true, message: '请输入密码，密码长度为6-12位', trigger: 'blur'}]
                }
            }
        },
        components:{
            MInput,
            MFormItem,
            MForm,
        },
        methods: {
            submitForm2() {
                this.$refs.loginForm2.validate(valid => {
                    if(valid){
                        alert('提交登录!');
                    } else {
                        console.log('校验失败！　');
                        return false;
                    }
                })
            }
        },
    }
</script>

<style scoped>

</style>