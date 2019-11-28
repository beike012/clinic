<template>
  <div class="head">
    <a href="/">
      <img src="@/assets/img/logo.png" alt />
    </a>
    <el-menu class="el-menu" mode="horizontal" router>
      <el-submenu index="1">
        <template slot="title">概况</template>
        <el-menu-item index="survey">医院简介</el-menu-item>
        <el-menu-item index="1-2">领导团队</el-menu-item>
        <el-menu-item index="1-3">组织架构</el-menu-item>
        <el-menu-item index="1-4">今昔协和</el-menu-item>
        <el-menu-item index="1-5">协和院史馆</el-menu-item>
        <el-menu-item index="1-6">所获荣誉</el-menu-item>
        <el-menu-item index="1-7">医疗机构营业许可</el-menu-item>
      </el-submenu>
      <el-submenu index="2">
        <template slot="title">新闻</template>
        <el-menu-item index="2-1">重大新闻</el-menu-item>
        <el-menu-item index="2-2">医院动态</el-menu-item>
        <el-menu-item index="2-3">医学前沿</el-menu-item>
        <el-menu-item index="2-4">媒体聚焦</el-menu-item>
        <el-menu-item index="2-5">人文关怀</el-menu-item>
        <el-menu-item index="2-6">协和院报</el-menu-item>
        <el-menu-item index="2-7">视频新闻</el-menu-item>
      </el-submenu>
      <el-submenu index="3">
        <template slot="title">医疗</template>
        <el-menu-item index="3-1">协和医师</el-menu-item>
        <el-menu-item index="3-2">科室导航</el-menu-item>
        <el-menu-item index="3-3">质控中心</el-menu-item>
        <el-menu-item index="3-4">医疗成果</el-menu-item>
      </el-submenu>
      <el-submenu index="4">
        <template slot="title">教育</template>
        <el-menu-item index="4-1">教育动态</el-menu-item>
        <el-menu-item index="4-2">临床医学博士后项目</el-menu-item>
        <el-menu-item index="4-3">本科教育</el-menu-item>
        <el-menu-item index="4-4">研究生教育</el-menu-item>
        <el-menu-item index="4-5">住院医师</el-menu-item>
        <el-menu-item index="4-6">专科医师</el-menu-item>
        <el-menu-item index="4-7">继续教育</el-menu-item>
        <el-menu-item index="4-8">学系及教研室简介</el-menu-item>
      </el-submenu>
      <el-submenu index="5">
        <template slot="title">科研</template>
        <el-menu-item index="5-1">科研动态</el-menu-item>
        <el-menu-item index="5-2">科研平台</el-menu-item>
        <el-menu-item index="5-3">科研成果展示</el-menu-item>
      </el-submenu>
      <el-submenu index="6">
        <template slot="title">护理</template>
        <el-menu-item index="6-1">护理概况</el-menu-item>
        <el-menu-item index="6-2">护理新闻</el-menu-item>
        <el-menu-item index="6-3">教学科研</el-menu-item>
        <el-menu-item index="6-4">国际护理学术高峰论坛</el-menu-item>
        <el-menu-item index="6-5">协和护理之音</el-menu-item>
        <el-menu-item index="6-6">所获荣誉</el-menu-item>
      </el-submenu>
      <el-submenu index="7">
        <template slot="title">党建</template>
        <el-menu-item index="7-1">基层党建</el-menu-item>
        <el-menu-item index="7-2">廉政建设</el-menu-item>
        <el-menu-item index="7-3">职工之家</el-menu-item>
        <el-menu-item index="7-4">医学新青年</el-menu-item>
        <el-menu-item index="7-5">患者心声</el-menu-item>
      </el-submenu>
      <el-menu-item index="8">招聘</el-menu-item>
    </el-menu>
    <el-button-group>
      <el-button type="primary" size="medium" plain>协和医院杂志</el-button>
      <el-button type="primary" size="medium" plain>协和院服</el-button>
      <el-button type="primary" size="medium" plain>院史馆</el-button>
      <el-button type="primary" size="medium" plain icon="el-icon-share" title="分享"></el-button>
      <el-popover width="300" trigger="click">
        <div class="search">
          <el-input
            placeholder="请输入您要搜索的内容"
            v-model="search"
            class="input-with-select"
            prefix-icon="el-icon-search"
            clearable
          >
            <el-button type="primary" plain slot="append">搜索</el-button>
          </el-input>
        </div>
        <el-button
          type="primary"
          size="medium"
          plain
          icon="el-icon-search"
          title="搜索"
          slot="reference"
        ></el-button>
      </el-popover>
    </el-button-group>
  </div>
</template>

<script>
export default {
  name: "myhead",
  data() {
    return {
      search: ""
    };
  },
  methods: {}
};
</script>
<style lang="less">
.head {
  padding: 10px 0;
  display: flex;
  justify-content: center;
  .el-menu {
    // width: 40%;
    display: flex;
    justify-content: space-between;
    margin: 0 10px;
    .el-menu-item {
      font-size: 18px;
    }
    .el-submenu__title {
      font-size: 18px;
    }
  }
  img {
    height: 60px;
  }
  .el-button-group {
    display: flex;
    align-items: center;
  }
  .search {
    .el-button {
      border-top-left-radius: 0;
      border-bottom-left-radius: 0;
    }
  }
}
.el-menu.el-menu--horizontal {
  border-bottom: 0 !important;
}
</style>
