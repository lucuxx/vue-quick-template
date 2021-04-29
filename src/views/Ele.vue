<template>
  <div class="container">
      <div class="side">Menu</div>
      <div class="main">
          <el-tabs v-model="activeName" @tab-click="handleClick">
                <el-tab-pane label="用户管理" name="table">
                    <test-view></test-view>
                </el-tab-pane>
                <el-tab-pane label="配置管理" name="list">
                    <div class="test">test</div>
                </el-tab-pane>
            </el-tabs>
      </div>
  </div>
</template>

<script>
// import TableView from '@/components/TableView.vue'
import TestView from '@/components/TestView.vue'
export default {
    components:{TestView},
    data(){
        return {
            activeName:'table'
        }
    }
}
</script>

<style lang="scss" scoped>
.container  {
    width:100%;
    height:100%;
    height:calc(100vh - 135px);
    display:flex;
    .side{
        flex-basis: 200px;
        min-width:200px;
        background:#fff;
        margin-right:3px;
        // height:calc(100vh - 135px);
    }
    .main{
        flex-grow: 1;
        background: pink;
        overflow-x:auto;
        // height:calc(100% -px);
        height:100%;
        .test{
        width:150%;height:100%;background:green;overflow-x:auto;}
    }
}

</style>