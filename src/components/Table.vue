<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    :row-class-name="tableRowClassName"
  >
    <el-table-column prop="id" label="id" width="180" />
    <el-table-column prop="name" label="name" width="180" />
    <el-table-column prop="gender" label="gender" />
  </el-table>

  <el-row class="mb-4">
    <el-button type="success" round>增加数据</el-button>
    <el-button type="danger" round>删除数据</el-button>
    <el-button type="primary" round>查找数据</el-button>
    <el-button type="warning" round>改动数据</el-button>
  </el-row>
</template>

<script>
import axios from 'axios';

export default {
    created: function () {
        axios.get("http://localhost:8088/user/get").then((response) => {
            this.tableData = response.data
        })
    },
    data() {
        return {
            tableData: []
        }
    },
}
</script>

<style>

</style>