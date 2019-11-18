<template>
  <div id="app">
    <my-head></my-head>
    <router-view></router-view>
    <my-foot></my-foot>
  </div>
</template>

<script>
import MyHead from '@/components/head'
import MyFoot from '@/components/foot'
export default {
  name: "app",
  components: {
    MyHead,
    MyFoot
  }
};
</script>

<style lang="less">
.heart{
  width: 1230px;
  margin: 0 auto;
  overflow: hidden;
}
</style>