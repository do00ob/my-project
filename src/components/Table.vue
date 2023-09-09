<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    :row-class-name="tableRowClassName"
    :header-cell-style="{ background: '#f2f5fc',color:'#55555'}"
    border
  >
    <el-table-column prop="id" label="ID" width="120" align="center" />
    <el-table-column prop="name" label="姓名" width="100" align="center"/>
    <el-table-column prop="gender" label="性别" align="center">
      <template #default="scope">
        <el-tag :type="scope.row.gender === '男'? 'danger' : 'sucesss'" disable-transitions>{{scope.row.gender === '男' ? '男':'女'}}</el-tag>
      </template>
    </el-table-column>
    <el-table-column prop="operate" label="操作" align="center">
      <template #default="scope">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-row class="mb-4">
    <el-button type="success" round>增加数据</el-button>
    <el-button type="danger" round>删除数据</el-button>
    <el-button type="primary" round>查找数据</el-button>
    <el-button type="warning" round>改动数据</el-button>
  </el-row>
  <div class="demo-pagination-block">
    <div class="demonstration"></div>
    <el-pagination
      v-model:current-page="pageNum"
      v-model:page-size="pageSize"
      :page-sizes="[100, 200, 300, 400]"
      :small="small"
      :disabled="disabled"
      :background="background"
      layout="total, sizes, prev, pager, next, jumper"
      :total="total"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    />
  </div>
</template>

<script>
import axios from 'axios';

export default {
    methods: {
      tableRowClassName({row, rowIndex}) {
        if (rowIndex%4 === 1) {
          return 'warning-row';
        } else if (rowIndex%4 === 3) {
          return 'success-row';
        }
        return '';
      },
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      },
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    },
    created: function () {
        //这个=>的作用是让该匿名函数内的this的作用域能和created平级 不用=>作用域会被限制在函数体内
        axios.get("http://localhost:8088/user/get").then((response) => {
            this.tableData = response.data
        })
    },
    data() {
        return {
            tableData: [],
            pageSize:10,
            pageNum:1,
            total:0,
        }
    },
    
}


</script>

<style>
  main.el-main {
    padding: 0;
}
</style>