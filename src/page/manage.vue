<template>
  <div class="manage_page">
    <el-container>
      <!-- 侧边栏 -->
      <!-- 侧边栏 -->
      <el-aside width="150px">
        <el-menu
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
            background-color=rgb(50,64,87)
            text-color="#bfcbd9"
            active-text-color="#ffd04b">
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span class="myindex" slot="title">首页</span>
          </el-menu-item>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>数据管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>数据管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
        </el-menu>

      </el-aside>
      <el-container>
        <el-header>
          <el-breadcrumb separator="/">
            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
            <el-breadcrumb-item v-for="(item,index) in $route.meta" :key="index"><a href="/">{{item}}</a></el-breadcrumb-item>
          </el-breadcrumb>
          
        </el-header>
        <el-main>Main</el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  name: '',

  data () {
    return {
    }
  },

  methods: {}
}
</script>

<style lang='less' rel='stylesheet/less'>
  .manage_page{
    height:100%;
    width: 100%;
    background-color: pink;
  }
  // 布局
  .el-container{
    width: 100%;
    height: 100%;
    .el-header{
    background-color:#EFF2F7;
    color: #333;
    text-align: center;
    line-height: 60px;
    }
  
    .el-aside {
      background-color:rgb(50,64,87);
      color: #333;
      text-align: center;
      height:100%;
      .myindex,
      .el-icon-menu:before{
        color:#20a0ff;
      }
      .el-submenu,
      .el-menu-item{
        width:151px;
        text-align:left;
        i{
          color:#bfcbd9;
        }
      }
      .el-menu-item:hover,
      .el-submenu__title:hover{
        background-color:#48576a!important;
      }
      .el-submenu__icon-arrow{
        font-size:14px;
      }
      .el-menu-item-group__title{
        padding:0;
      }
      .el-submenu .el-menu-item{
        min-width:200px;
        background-color: #1e252e!important;
      }
      .el-menu-item-group>ul{
        
      }
      
    }
    .el-main {
      background-color:#fff;
      color: #333;
      text-align: center;
      line-height: 200px;
      height:100%;
    }
  }
  
</style>
