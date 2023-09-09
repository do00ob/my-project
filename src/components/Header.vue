<template>
    <el-header style="text-align: center; font-size: 35px">
        <div class="toolbar">
          <el-dropdown>
            <el-icon style="margin-right: 8px; margin-top: 1px"
              ><setting
            /></el-icon>
            <template #dropdown>
              <el-dropdown-menu>
                <el-dropdown-item>View</el-dropdown-item>
                <el-dropdown-item>Add</el-dropdown-item>
                <el-dropdown-item>Delete</el-dropdown-item>
              </el-dropdown-menu>
            </template>
          </el-dropdown>
          <span>学生管理系统</span>
        </div>
      </el-header>
</template>

<style>
  .el-header {
    background-color: #b2d0f7;
    color: #333;
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
  }

</style>
 
 <script>
import { ref } from 'vue'
import { Menu as IconMenu, Message, Setting } from '@element-plus/icons-vue'
import axios from 'axios';
 
 export default {
   methods: {
   },
     data() {
         return {

         }
     },
     
 }
 
 
 </script>