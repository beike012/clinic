<template>
  <div class="home">
    <div class="carousel">
      <el-carousel trigger="click" height="630px">
        <el-carousel-item v-for="(item, index) in carouselPics" :key="index">
          <a href="javasrcipt:;" :style="{ backgroundImage: `url(${item})` }"></a>
        </el-carousel-item>
      </el-carousel>
    </div>
    <div class="heart">
      <!-- tips -->
      <el-row :gutter="10" class="tips">
        <el-col :span="6">
          <el-card class="move_card card1" :class="{start}">
            <img src="@/assets/img/门诊出诊表.png" alt />
            <span>门诊出诊表</span>
          </el-card>
        </el-col>
        <el-col :span="6">
          <el-card class="move_card card2" :class="{start}">
            <img src="@/assets/img/就医须知.png" alt />
            <span>就医须知</span>
          </el-card>
        </el-col>
        <el-col :span="6">
          <el-card class="move_card card3" :class="{start}">
            <img src="@/assets/img/医院位置.png" alt />
            <span>医院位置</span>
          </el-card>
        </el-col>
        <el-col :span="6">
          <el-card class="move_card card4" :class="{start}">
            <img src="@/assets/img/专科专病.png" alt />
            <span>专科专病</span>
          </el-card>
        </el-col>
      </el-row>
      <!-- 新闻 -->
      <el-row :gutter="30">
        <el-col :span="16">
          <div class="newsTab">
            <el-menu class="el-menu" mode="horizontal">
              <el-menu-item index="1" class="bigNews">重大新闻</el-menu-item>
              <el-menu-item index="2">医院动态</el-menu-item>
              <el-menu-item index="3">医学前沿</el-menu-item>
              <el-menu-item index="4">人文关怀</el-menu-item>
              <el-menu-item index="5">媒体聚焦</el-menu-item>
            </el-menu>
            <div class="more">
              <el-button type="primary" size="medium" plain>查看更多</el-button>
            </div>
          </div>
          <div class="newsPic">
            <el-row :gutter="10" class="pics">
              <el-col :span="12">
                <a href="javascript:;">
                  <img src="@/assets/img/3.jpg" alt width="100%" />
                  <p>【新华社】孙春兰出席纳米比亚“光明行”活动</p>
                </a>
              </el-col>
              <el-col :span="12">
                <a href="javascript:;">
                  <img src="@/assets/img/3.jpg" alt width="100%" />
                  <p>2018年度中国医院排行榜发布，北京协和医院连续...</p>
                </a>
              </el-col>
            </el-row>
            <ul class="list">
              <li>
                <div class="date">
                  <p class="day">13</p>
                  <p class="year">2019.11</p>
                </div>
                <div class="cont">
                  <h3 class="h3">
                    <a href>【新华社】孙春兰出席纳米比亚“光明行”活动</a>
                  </h3>
                  <p class="p"></p>
                </div>
              </li>
              <li>
                <div class="date">
                  <p class="day">11</p>
                  <p class="year">2019.11</p>
                </div>
                <div class="cont">
                  <h3 class="h3">
                    <a href>2018年度中国医院排行榜发布，北京协和医院连续十年蝉联榜首</a>
                  </h3>
                  <p class="p"></p>
                </div>
              </li>
              <li>
                <div class="date">
                  <p class="day">15</p>
                  <p class="year">2019.10</p>
                </div>
                <div class="cont">
                  <h3 class="h3">
                    <a href>北京协和医院召开第四批“组团式”援藏医疗队表彰会</a>
                  </h3>
                  <p class="p"></p>
                </div>
              </li>
            </ul>
          </div>
        </el-col>
        <el-col :span="8">
          <div class="newsTab">
            <div class="bigNews">医院公告</div>
            <div class="more">
              <el-button type="primary" size="medium" plain>查看更多</el-button>
            </div>
          </div>
          <div class="newsCard">
            <el-card class="box-card" v-for="(item,index) in notice" :key="index">
              <a href>{{ item }}</a>
            </el-card>
          </div>
        </el-col>
      </el-row>
      <!-- 动画卡片 -->
      <div class="len_home2" :class="{show}">
        <div class="box b1 transition translateY_100" style="transition-delay: 0s;">
          <div class="head">
            <h1 class="h1">医疗</h1>
          </div>
          <ul class="list">
            <li>
              <a href>
                <img class="ico" src="@/assets/img/医师.png" />
                <span class="txt">协和医师</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/导航.png" />
                <span class="txt">科室导航</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/中心.png" />
                <span class="txt">质控中心</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/成果.png" />
                <span class="txt">医疗成果</span>
              </a>
            </li>
          </ul>
          <div class="news">
            <a href>
              <h2 class="h2">一线快递</h2>
            </a>
            <ul>
              <li>
                <a href>北京协和医院肝脏外科顺利完成巨大肝癌切除术</a>
                <p class="date">2018.11.29</p>
              </li>
              <li>
                <a href>协和国际远程会诊：搭建中外顶级医生的对话平台</a>
                <p class="date">2018.10.11</p>
              </li>
            </ul>
          </div>
        </div>
        <div class="box b2 transition translateY_100" style="transition-delay: 0.3s;">
          <div class="head">
            <h1 class="h1">教育</h1>
          </div>
          <ul class="list">
            <li>
              <a href>
                <img class="ico" src="@/assets/img/本科教育.png" />
                <span class="txt">本科教育</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/研究生教育.png" />
                <span class="txt">研究生教育</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/住院医师.png" />
                <span class="txt">住院医师</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/专科医师.png" />
                <span class="txt">专科医师</span>
              </a>
            </li>
          </ul>
          <div class="news">
            <a href>
              <h2 class="h2">教育动态</h2>
            </a>
            <ul>
              <li>
                <a href>学习如何成长为合格的医学教育者——芝加哥大学国际医学教育者项目学习有感</a>
                <p class="date">2019.10.17</p>
              </li>
              <li>
                <a href>北京协和医院举行2019级临床医学博士后首次班会</a>
                <p class="date">2019.10.16</p>
              </li>
            </ul>
          </div>
        </div>
        <div class="box b3 transition translateY_100" style="transition-delay: 0.6s;">
          <div class="head">
            <h1 class="h1">科研</h1>
          </div>
          <ul class="list">
            <li>
              <a href>
                <img class="ico" src="@/assets/img/平台.png" />
                <span class="txt">科研平台</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/科研成果.png" />
                <span class="txt">重大科研成果</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/支持.png" />
                <span class="txt">科技支持</span>
              </a>
            </li>
          </ul>
          <div class="news">
            <a href>
              <h2 class="h2">科研动态</h2>
            </a>
            <ul>
              <li>
                <a href>国家卫生健康委内分泌重点实验室第三届学术委员会第二次会议顺利召开</a>
                <p class="date">2019.08.19</p>
              </li>
              <li>
                <a href>北京协和医院关于“一种用于局部氧疗的供氧装置”专利技术的科研成果转让</a>
                <p class="date">2019.06.03</p>
              </li>
              <li>
                <a href>北京协和医院关于“一种瘦素的凝胶缓释系统及其应用”专利技术的科研成果转让公示</a>
                <p class="date">2019.04.15</p>
              </li>
            </ul>
          </div>
        </div>
        <div class="box b4 transition translateY_100" style="transition-delay: 0.9s;">
          <div class="head">
            <h1 class="h1">护理</h1>
          </div>
          <ul class="list">
            <li>
              <a href>
                <img class="ico" src="@/assets/img/概况.png" />
                <span class="txt">护理概况</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/新闻.png" />
                <span class="txt">护理新闻</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/教研.png" />
                <span class="txt">教学科研</span>
              </a>
            </li>
            <li>
              <a href>
                <img class="ico" src="@/assets/img/之音.png" />
                <span class="txt">协和护理之音</span>
              </a>
            </li>
          </ul>
          <div class="news">
            <a href>
              <h2 class="h2">护理新闻</h2>
            </a>
            <ul>
              <li>
                <a href>协和外科举办“玫瑰人生，你我同行”外科护理科普活动</a>
                <p class="date">2019.10.27</p>
              </li>
              <li>
                <a href>协和营养专科护理小组举办“爱注营养，管喂人生”科普活动</a>
                <p class="date">2019.10.27</p>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  components: {},
  data() {
    return {
      carouselPics: [
        "https://www.pumch.cn/Uploads/Picture/2019/09/23/s5d888a398e6cf.png",
        "https://www.pumch.cn/Uploads/Picture/2019/11/11/s5dc92b4cbc717.jpg",
        "https://www.pumch.cn/Uploads/Picture/2019/11/11/s5dc92b6316d73.jpg",
        "https://www.pumch.cn/Uploads/Picture/2019/11/11/s5dc92b6a7e29e.jpg",
        "https://www.pumch.cn/Uploads/Picture/2019/11/11/s5dc92b709c34b.jpg"
      ],
      notice: [
        "北京协和医院试剂采购延期公告",
        "11月12日世界糖尿病日科普和义诊活动预告",
        "内科楼血液净化中心工程DSA项目环境影响评价信息公示",
        "北京协和医院试剂采购公告（第28期）",
        "北京协和医院试剂采购延期公告"
      ],
      show: false,
      start: false
    };
  },
  methods: {},
  mounted() {
    window.addEventListener("scroll", () => {
      if (window.scrollY > 600) this.show = true;
    });
    this.start = true;
  }
};
</script>

<style lang="less">
.home {
  .carousel {
    position: relative;
    .el-carousel__item {
      a {
        display: block;
        height: 100%;
        background: no-repeat center;
        background-size: cover;
      }
    }
  }
  .newsTab {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 61px;
    margin-bottom: 10px;
    .bigNews {
      font-size: 20px;
      color: #909399;
    }
    .more {
      display: flex;
      align-items: center;
    }
  }
  .newsPic {
    .pics {
      margin-bottom: 20px;
      a {
        display: block;
        color: #fff;
        position: relative;
        overflow: hidden;
        display: flex;
        justify-content: center;
        p {
          overflow: hidden;
          text-overflow: ellipsis;
          text-align: center;
          width: 100%;
          position: absolute;
          bottom: 0;
        }
        img {
          transition: all, 1s;
        }
        img:hover {
          transform: scale(1.1, 1.1);
        }
      }
    }
    .list {
      padding-left: 14px;
      padding-top: 11px;
      background: url("../../assets/img/ruler.jpg") 0 0 repeat-y;
      li:hover {
        color: #01763a;
      }
      li {
        overflow: hidden;
        color: #333;
        margin-top: 20px;
        .date {
          float: left;
          width: 110px;
          text-align: center;
          .day {
            font-family: Arial;
            font-size: 55px;
            line-height: 1;
          }
          .year {
            font-family: Arial;
            font-size: 16px;
            line-height: 18px;
          }
        }
        .cont {
          overflow: hidden;
          .h3 {
            margin-bottom: 6px;
            font-size: 18px;
            font-weight: normal;
            line-height: 32px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            a {
              color: #333;
            }
            a:hover {
              color: #01763a;
            }
          }
          .p {
            font-size: 12px;
            color: #707070;
            line-height: 18px;
          }
        }
      }
    }
  }
  .newsCard {
    height: 586px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .box-card {
      height: 20%;
      margin-bottom: 15px;
      a {
        color: #333;
      }
      a:hover {
        color: #01763a;
      }
    }
  }
}
.heart {
  .tips{
    margin-top: 10px;
  }
  .move_card {
    width: 300px;
    height: 207px;
    cursor: pointer;
    opacity: 0;
    transition: opacity 1.3s, transform 1.3s;
    &:hover {
      img {
        animation: rot 0.5s;
      }
    }
    .el-card__body {
      padding: 0;
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #fff;
      font-size: 18px;
      img {
        margin-bottom: 5px;
      }
    }
  }
  .card1 {
    background: url("../../assets/img/bg1.jpg") no-repeat center;
    transform: translateX(-50px);
  }
  .card2 {
    background-color: #e5ca8f;
    transform: translateX(-100px);
  }
  .card3 {
    background: url("../../assets/img/bg3.jpg") no-repeat center;
    transform: translateX(-150px);
    .el-card__body {
      color: #474747;
    }
  }
  .card4 {
    background-color: #01763a;
    transform: translateX(-200px);
  }
  .start {
    opacity: 1;
    transform: translateX(0);
  }
}
@keyframes rot {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(5deg);
  }
  50% {
    transform: rotate(-5deg);
  }
  75% {
    transform: rotate(5deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
.len_home2 {
  position: relative;
  margin-bottom: 138px;
  height: 665px;
}
.len_home2 .box {
  position: absolute;
  padding: 50px 36px;
  -webkit-box-shadow: 0px 0px 18px 0px rgba(0, 0, 0, 0.14);
  box-shadow: 0px 0px 18px 0px rgba(0, 0, 0, 0.14);
  color: #fff;
  -webkit-box-sizing: content-box;
  box-sizing: content-box;
}
.len_home2 .box.b1 {
  left: 0;
  top: 45px;
  width: 250px;
  padding-right: 70px;
  background-color: #55a5aa;
}
.len_home2 .box.b1 .more {
  border-color: #6fb2dd;
}
.len_home2 .box.b1 .list li,
.len_home2 .box.b1 .news {
  border-color: #5dc2c8;
}
.len_home2 .box.b2 {
  left: 316px;
  top: 95px;
  width: 236px;
  padding-right: 60px;
  background-color: #e5ca90;
}
.len_home2 .box.b2 .more {
  border-color: #ffe2a2;
}
.len_home2 .box.b2 .list li,
.len_home2 .box.b2 .news {
  border-color: #ffe2a2;
}
.len_home2 .box.b3 {
  left: 625px;
  top: 0;
  width: 221px;
  padding-right: 93px;
  background-color: #fff;
  color: #333;
}
.len_home2 .box.b3 .h1,
.len_home2 .box.b3 .h2,
.len_home2 .box.b3 li a {
  color: #333;
}
// .len_home2 .box.b3 .more{ border-color: #ddd; background-image: url(../image/xf/png7.png);}
.len_home2 .box.b3 .list li,
.len_home2 .box.b3 .news {
  border-color: #ddd;
}
.len_home2 .box.b4 {
  right: 0;
  top: 57px;
  width: 250px;
  padding-right: 30px;
  background-color: #01763a;
}
.len_home2 .box.b4 .more {
  border-color: #fff;
}
.len_home2 .box.b4 .list li,
.len_home2 .box.b4 .news {
  border-color: #2e9448;
}
.len_home2 .head {
  margin-bottom: 25px;
  overflow: hidden;
}
.len_home2 .h1 {
  font-size: 24px;
  line-height: 25px;
  color: #fff;
}
.len_home2 .h2 {
  margin-bottom: 22px;
  font-size: 18px;
  line-height: 1;
  color: #fff;
}
// .len_home2 .more{ float: right; width: 25px; height: 25px; border: 1px solid; border-radius: 4px; background: url(../image/xf/png6.png) center no-repeat;}
.len_home2 .more:hover {
  opacity: 0.8;
}
// .len_home2 .list{}
.len_home2 .list li {
  margin-bottom: 5px;
  padding: 9px 30px;
  border: 1px solid;
  border-radius: 8px;
  font-size: 14px;
}
.len_home2 .list li:hover {
  opacity: 0.8;
}
.len_home2 .ico {
  display: inline-block;
  vertical-align: middle;
  width: 36px;
  height: 33px;
}
.len_home2 .txt {
  margin-left: 25px;
  display: inline-block;
  vertical-align: middle;
}
.len_home2 .news {
  margin-top: 10px;
  padding: 22px 22px 22px 28px;
  border: 1px solid;
  border-radius: 8px;
}
// .len_home2 .news ul{}
.len_home2 .news li {
  font-size: 12px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.len_home2 .news li + li {
  margin-top: 16px;
}
.len_home2 .news li:hover {
  opacity: 0.8;
}
.len_home2 .date {
  margin-top: 8px;
  font-family: Arial;
}
.len_home2 .box li a {
  color: #fff;
}
//4 cards transition
.transition {
  opacity: 0;
  transform: translate(0, 100px);
  transition: opacity 2s, transform 2s;
}
.show .transition {
  opacity: 1;
  transform: translate(0, 0);
}
</style>
