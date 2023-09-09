<template>
     <el-col :span="120">
    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      background-color="#545c64"
      text-color="#fff"
      style="height: 150vh;"
      active-text-color="#ffd04b">
      
      <el-menu-item index="1">
        <el-icon><location /></el-icon>
        <i class="el-icon-menu"></i>
        <span>导航一</span>
      </el-menu-item>
      <el-menu-item index="2">
        <el-icon><Menu /></el-icon>
        <i class="el-icon-menu"></i>
        <span>导航二</span>
      </el-menu-item>
      <el-menu-item index="3">
        <el-icon><document /></el-icon>
        <i class="el-icon-document"></i>
        <span>导航三</span>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon><setting /></el-icon>
        <i class="el-icon-setting"></i>
        <span>导航四</span>
      </el-menu-item>
    </el-menu>
  </el-col>
</template>
  
<style scoped>
.layout-container-demo .el-header {
  position: relative;
  background-color: var(--el-color-primary-light-7);
  color: var(--el-text-color-primary);
}
.layout-container-demo .el-aside {
  color: var(--el-text-color-primary);
  background: var(--el-color-primary-light-8);
}
.layout-container-demo .el-menu {
  border-right: none;
}
.layout-container-demo .el-main {
  padding: 0;
}
.layout-container-demo .toolbar {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  right: 20px;
}
</style>

  <script>
  import axios from 'axios';
  
  export default {
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    },
      data() {
          return {

          }
      },
      
  }
  
  
  </script>
  
  <style>
  
  </style>