<template>
  <div class="app-container">
    <div >
        <el-breadcrumb separator-class="el-icon-arrow-right">
        <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
        <el-breadcrumb-item>活动管理</el-breadcrumb-item>
      </el-breadcrumb>
    </div>
    <el-tabs type="border-card">
        <el-tab-pane label="用户管理">
          <User></User>
        </el-tab-pane>
        <el-tab-pane label="配置管理">配置管理</el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import User from './view/User'
export default {
  data () {
    return {
    }
  },
  components: {
    User
  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.el-breadcrumb{
  line-height: 20px;
  margin: 0px 0px 10px auto;
}
</style>
