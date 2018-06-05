<template>
  <div class="login_page">
    <h1>cms后台管理系统</h1>
    <div class="login_form">
      <!-- 表格绑定ruleForm2数据 -->
      <!-- 表格绑定验证规则rules2 -->
      <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
        <el-form-item prop="account">
          <el-input v-model.number="ruleForm.account" placeholder="用户名"></el-input>
        </el-form-item>
        <el-form-item  prop="pass">
          <el-input type="password" v-model="ruleForm.pass" auto-complete="off" placeholder="密码"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
          <!-- <el-button @click="resetForm('ruleForm')">重置</el-button> -->
        </el-form-item>
        <div class="tip">
          <p>温馨提示：<br>未登录过的新用户，自动注册<br>注册过的用户可凭账号密码登录</p>
        </div>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    //1-验证账号
    var checkAccount = (rule,value,callback)=>{
      //不能账号为空
      if(!value){
        return callback(new Error('账号不能为空'));
      }else{
        callback();
      }
    };
    //2-验证密码
    var validatePass=(rule,value,callback)=>{
      //判断密码不为空
      if(!value){
        return callback(new Error('请输入密码'));
      }else{
        callback();
      }
    };
    return {
      ruleForm:{
        account:'',
        pass:''
      },
      rules:{
        account:[
          {validator:checkAccount,trigger:'blur'}
        ],
        pass:[
          { validator:validatePass,trigger:'blur'}
        ]
      },

    }
  },

  methods: {
    submitForm(){
      console.log('已登录');
      this.$router.push('/manage');
    }
  }
}
</script>

<style lang='less' rel='stylesheet/less'>
  body{
    background-color:#324057;
  }
  .login_page{
    width: 370px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    h1{
    color:yellow;
    margin:40px;
    color:#fff;
    text-align:center;
    font-weight:400;
    }
    .login_form{
      width: 100%;
      height: 280px;
      background-color: #fff;
      padding-top:20px;
      box-sizing: border-box;
      border-radius:5px;
    }
    .el-form-item__content{
      margin:0!important;
      padding:0 20px;
    }
    .el-button{
      width: 100%;
    }
    .tip{
      text-align:center;
      color:red;
      font-size:12px;
    }
    .el-form-item__error{
      padding-left:20px;
    }
  }
</style>


