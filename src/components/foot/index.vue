<template>
  <div class="foot">
    <div class="heart links flex">
      <span>友情链接：&nbsp;</span>
      <a href>中华人民共和国国家卫生健康委员会</a>
      <i class="shu"></i>
      <a href>北京市卫生健康委员会</a>
      <i class="shu"></i>
      <a href>中国医学科学院</a>
      <i class="shu"></i>
      <a href>北京协和医学基金会</a>
      <i class="shu"></i>
      <a href>协和科技开发有限责任公司</a>
      <i class="shu"></i>
      <a href>协和化妆品</a>
    </div>
    <i class="heng"></i>
    <div class="heart web_msg flex">
      <div class="left">
        <div class="flex">
          <a href>网站地图</a>
          <i class="shu"></i>
          <a href>关于我们</a>
        </div>
        <p>地&#12288;&#12288;址：（东单院区）北京市东城区帅府园一号，100730；（西单院区）北京市西城区大木仓胡同41号，100032</p>
        <p>服务热线： 010-69156114</p>
      </div>
      <div class="right">
          <p>Copyright 北京协和医院 All Rights Reserved. 本站内容仅供参考，不作为诊断及医疗依据</p>
          <p>京ICP 备 05067313号-1 文保网安备案号：1101010023 京卫网审字【2014】第39号</p>
          <p>网站建设： <a href="">深圳贝克科技</a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "myfoot"
};
</script>

<style lang="less" scoped>
.foot {
  background: url("../../assets/img/foot.jpg") no-repeat center top;
  font-size: 12px;
  color: #b2b2b2;
  line-height: 20px;
  a {
    color: #b2b2b2;
  }
  .flex {
    display: flex;
    align-items: center;
  }
  .links {
    height: 70px;
  }
  .shu {
    display: block;
    width: 1px;
    height: 12px;
    background-color: #b2b2b2;
    margin: 0 20px;
  }
  .heng {
    display: block;
    width: 100%;
    height: 1px;
    background-color: #585858;
  }
  .web_msg {
    padding: 30px 0;
    justify-content: space-between;
    .right{
        width: 40%;
        text-align: right;
    }
  }
}
</style>