<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <el-container id="basicPage">
      <el-header style="padding: 0px">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal"
                 style="background-color: dodgerblue; margin: 0 0 0 0">
          <el-menu-item index="1" style="color:white">志愿填报</el-menu-item>
          <el-menu-item index="4" style="color:white">咨询</el-menu-item>
          <el-menu-item index="3" style="float: right; color: #fcf16e">消息中心</el-menu-item>
          <el-button type="success" round style="height: auto; position: absolute; right: 10px;margin-top: 10px"> 个人中心
          </el-button>
        </el-menu>

      </el-header>

      <el-container>
        <el-aside width="20%">
          <div id="tableData">
            <el-menu
                style="min-height: 200vh; width: 150px"
                :uniqueOpened="true"
                default-active="2"
                class="el-menu-vertical-demo"
                @open="handleOpen"
                @close="handleClose"
                background-color="#545c64"
                text-color="#fff"
                active-text-color="#ffd04b">
              <el-sub-menu index="1">
                <template #title>
                  <i class="el-icon-location"></i>
                  <span>模拟填报</span>
                </template>
                <el-menu-item-group>
                  <template #title>分组一</template>
                  <el-menu-item index="1-1">选项1</el-menu-item>
                  <el-menu-item index="1-2">选项2</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group title="分组2">
                  <el-menu-item index="1-3">选项3</el-menu-item>
                </el-menu-item-group>
                <el-sub-menu index="1-4">
                  <template #title>选项4</template>
                  <el-menu-item index="1-4-1">选项1</el-menu-item>
                </el-sub-menu>
              </el-sub-menu>
              <el-menu-item index="2">
                <i class="el-icon-menu"></i>
                <template #title>估分</template>
              </el-menu-item>
              <el-menu-item index="3" disabled>
                <i class="el-icon-document"></i>
                <template #title>咨询</template>
              </el-menu-item>
              <el-menu-item index="4">
                <i class="el-icon-setting"></i>
                <template #title>特殊权限</template>
              </el-menu-item>
            </el-menu>
          </div>
        </el-aside>

        <el-main>
          <div id="table">
            <el-table
                :data="tableData"
                stripe>
              <el-table-column
                  prop="date"
                  label="日期"
                  fit
                  >
              </el-table-column>
              <el-table-column
                  prop="name"
                  label="姓名"
                  fit
                  >
              </el-table-column>
              <el-table-column
                  prop="address"
                  label="地址"
                  fit
                  >
              </el-table-column>
            </el-table>
          </div>
        </el-main>
        <el-backtop target=".page-component__scroll .el-scrollbar__wrap"></el-backtop>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      activeIndex: '1',
      activeIndex2: '1',
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄',
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄',
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }]
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    tableRowClassName({row, rowIndex}) {
      if (rowIndex === 1) {
        return 'warning-row';
      } else if (rowIndex === 3) {
        return 'success-row';
      }
      return '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.el-col {
  border-radius: 4px;
}

.bg-purple-dark {
  background: #99a9bf;
}

.bg-purple {
  background: #d3dce6;
}

.bg-purple-light {
  background: #e5e9f2;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}

.el-table .warning-row {
  background: oldlace;
}

.el-table .success-row {
  background: #f0f9eb;
}
</style>
