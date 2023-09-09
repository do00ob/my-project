<template>

  <div class="common-layout">
    <el-container>
      <el-header><myHeader/></el-header>
      <el-container>
        <el-aside width="150px"><myAside msg="ee"/></el-aside>
        <el-main><myTable msg="ee"/></el-main>
      </el-container>
    </el-container>
  </div>
  
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <ul>
    <!--li v-for="(data,index) in tableData" :key="index">{{data}}</li-->
  </ul>
  
  
</template>

<script >
import HelloWorld from './components/HelloWorld.vue'
import myTable from './components/Table.vue';
import myAside from './components/Aside.vue'
import myHeader from './components/Header.vue'



const tableRowClassName = ({
  row,
  rowIndex,
}) => {
  rowIndex = tableData.width
  if (rowIndex === 1) {
    return 'warning-row'
  } else if (rowIndex === 3) {
    return 'success-row'
  }
  return ''
}



export default {
  name: 'App',
  //在components里进行注册
  //注册完后就能在templete里使用对应名字的标签
  components: {
    //HelloWorld,
    myTable,
    myAside,
    myHeader
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.el-table .warning-row {
  --el-table-tr-bg-color: var(--el-color-warning-light-9);
}
.el-table .success-row {
  --el-table-tr-bg-color: var(--el-color-success-light-9);
}
</style>
