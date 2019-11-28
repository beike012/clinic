<template>
  <div class="toast" v-if="$route.name!=='home'">
      <span>您现在的位置：</span>
      <el-breadcrumb separator-class="el-icon-arrow-right">
        <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
        <el-breadcrumb-item :to="{ path: '/' }">活动管理</el-breadcrumb-item>
        <el-breadcrumb-item>活动列表</el-breadcrumb-item>
      </el-breadcrumb>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="less">
.toast{
  height: 30px;
  display: flex;
  justify-content: left;
  align-items: center;
  color: #707070;
  margin: 10px 0;
  .el-breadcrumb{
    font-size: 16px;
  }
  .el-breadcrumb__inner.is-link{
    color: #707070;
    font-weight: normal;
  }
}
</style>