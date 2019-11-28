<template>
  <div class="survey" @mousemove="mousemove" @mouseup="mouseup">
    <div class="heart">
      <toast></toast>
      <div class="introduction">
        <img src="@/assets/img/introduction.jpg" alt :class="{trans_img:trans_img}" />
        <el-card class="box-card" :class="{trans_card:trans_card}">
          <div class="head">
            <span>医院简介</span>
            <el-button size="small" round>西单院区</el-button>
          </div>
          <div class="body">
            <span>北京协和医院是集医疗、教学、科研于一体的现代化综合三级甲等医院，是国家卫生健康委指定的全国疑难重症诊治指导中心，最早承担高干保健和外宾医疗任务的医院之一，也是高等医学教育和住院医师规范化培训国家级示范基地，临床医学研究和技术创新的国家级核心基地。以学科齐全、技术力量雄厚、特色专科突出、多学科综合优势强大享誉海内外。在复旦大学医院管理研究所公布的“...</span>
          </div>
          <div class="foot">
            <el-button size="meadium" round>查看更多</el-button>
          </div>
        </el-card>
      </div>
      <div class="team">
        <p>领导团队</p>
        <img src="@/assets/img/leaderTeam.jpg" alt width="100%" />
        <div class="intro">
          <p>从左到右依次为：</p>
          <p>杨敦干副院长 韩丁副院长 张抒扬书记 柴建军副书记 赵玉沛院长 姜玉新书记（原） 李冬晶副院长 向炎珍总会计师 吴文铭副院长</p>
        </div>
      </div>
      <div class="now">
        <p>今昔协和</p>
        <div class="img" ref="img">
          <img src="@/assets/img/old.jpg" />
          <div class="mask" ref="mask" :style="maskStyle"></div>
          <div
            class="ctrl"
            ref="ctrl"
            @mousedown="mousedown"
            :style="ctrlStyle"
            @dragenter="prevent"
            @dragover="prevent"
          ></div>
        </div>
      </div>
      <div class="glory">
        <p>所获荣誉</p>
        <el-carousel height="310px" :interval="4000" arrow="never" ref="carousel">
          <div v-for="(a,o) in 2" :key="o">
            <el-carousel-item>
              <el-row :gutter="10">
                <el-col :span="6" v-for="(item,index) in carousel" :key="index">
                  <div class="col" v-if="index<4">
                    <div class="carousel-card">
                      <img :src="require(`@/assets/img/glory/${(index+1)}.jpg`)" alt />
                    </div>
                    <span>{{item}}</span>
                    <div class="line"></div>
                  </div>
                </el-col>
              </el-row>
            </el-carousel-item>
            <el-carousel-item>
              <el-row :gutter="10">
                <el-col :span="6" v-for="(item,index) in carousel" :key="index">
                  <div class="col" v-if="index>=4">
                    <div class="carousel-card">
                      <img :src="require(`@/assets/img/glory/${(index+1)}.jpg`)" alt />
                    </div>
                    <span>{{item}}</span>
                    <div class="line"></div>
                  </div>
                </el-col>
              </el-row>
            </el-carousel-item>
          </div>
          <div class="prev" @click="prev">
            <i></i>
          </div>
          <div class="next" @click="next">
            <i></i>
          </div>
        </el-carousel>
      </div>
    </div>
  </div>
</template>

<script>
import Toast from "@/components/toast";
export default {
  name: "survey",
  components: {
    Toast
  },
  data() {
    return {
      trans_img: true,
      trans_card: true,
      ctrlStyle: "",
      maskStyle: "",
      position: {
        init: "",
        initPosition: "",
        isMove: false,
        dropPosition: ""
      },
      carousel: [
        "中央国家机关先进基层党组织",
        "中国最佳医院排行榜 全国第一名",
        "全国住院医师规范化培训基地",
        "模范职工小家，北京市教工会先进教职工小家",
        "全国科普教育基地",
        "巾帼文明岗",
        "全国卫生系统抗击非典先进集体",
        "全国“三八”红旗集体"
      ]
    };
  },
  methods: {
    prev() {
      this.$refs.carousel.prev();
    },
    next() {
      this.$refs.carousel.next();
    },
    mousedown(e) {
      this.position.init = e.pageX;
      this.position.initPosition =
        this.$refs.ctrl.offsetLeft + this.$refs.ctrl.offsetWidth / 2;
      this.position.isMove = true;
    },
    mousemove(e) {
      if (!this.position.isMove) return;
      let move = this.position.init - e.pageX;
      this.position.dropPosition = this.position.initPosition - move;
      if (this.position.dropPosition < 0) {
        this.ctrlStyle = `left:0`;
        this.maskStyle = "width:100%";
      } else if (this.position.dropPosition > this.$refs.img.offsetWidth) {
        this.ctrlStyle = `left:${this.$refs.img.offsetWidth}px`;
        this.maskStyle = "width:0";
      } else {
        this.ctrlStyle = `left:${this.position.dropPosition}px`;
        this.maskStyle = `width:${this.$refs.img.offsetWidth -
          this.position.dropPosition}px`;
      }
    },
    mouseup() {
      this.position.isMove = false;
    },
    prevent(e) {
      e.preventDefault();
    }
  },
  created() {
    setTimeout(() => {
      this.trans_img = false;
      this.trans_card = false;
    }, 500);
  }
};
</script>

<style lang="less" scoped>
.survey {
  background: url("../../assets/img/jpg1.jpg");
  overflow: hidden;
  border-top: 1px solid #ddd;
  .heart {
    overflow: visible;
  }
  .introduction {
    position: relative;
    height: 540px;
    margin: 0 auto 100px;
    img {
      position: absolute;
      left: 0;
      top: 0;
      transform: translateX(0);
      opacity: 1;
      transition: all 2.5s;
    }
    .box-card {
      position: absolute;
      width: 615px;
      height: 387px;
      right: 0;
      bottom: 0;
      transform: translateX(0);
      opacity: 1;
      transition: all 2.2s;
      transition-delay: 0.3s;
      .head {
        display: flex;
        justify-content: space-between;
        background: url("../../assets/img/jpg4.jpg") no-repeat center;
        font-size: 24px;
        margin-bottom: 30px;
        .el-button {
          background-color: #01763a;
          color: #fff;
        }
        .el-button:hover {
          background-color: #349161;
        }
      }
      .body {
        margin-bottom: 30px;
        height: 200px;
      }
      .foot {
        .el-button:hover {
          background-color: #01763a;
          color: #fff;
        }
      }
    }
    .trans_img {
      transform: translateX(-140%);
      opacity: 0;
    }
    .trans_card {
      transform: translateX(140%);
      opacity: 0;
    }
  }
  p {
    text-align: center;
    font-size: 24px;
    color: #333;
    margin-bottom: 30px;
  }
  .team {
    margin-bottom: 100px;
    .intro {
      p {
        font-size: 16px;
        line-height: 24px;
        font-weight: normal;
        margin-top: 5px;
        margin-bottom: 5px;
        text-align: left;
      }
    }
  }
  .now {
    margin-bottom: 100px;
    .img {
      width: 100%;
      position: relative;
      overflow: hidden;
      img {
        width: 100%;
        display: block;
        user-select: none;
      }
      .mask {
        position: absolute;
        right: 0;
        top: 0;
        width: 50%;
        height: 100%;
        background: url("../../assets/img/new.jpg") no-repeat right;
        background-size: cover;
        z-index: 1;
      }
      .ctrl {
        position: absolute;
        left: 50%;
        top: 50%;
        margin-left: -26px;
        margin-top: -26px;
        width: 52px;
        height: 52px;
        background: url(../../assets/img/png11.png) center no-repeat;
        cursor: move;
        z-index: 2;
      }
    }
  }
  .glory {
    text-align: center;
    font-size: 14px;
    color: #333;
    .col {
      position: relative;
      &:hover {
        color: #01763a;
        &::after {
          color: #01763a;
        }
      }
      &::after {
        content: "";
        position: absolute;
        left: 0;
        right: 0;
        bottom: -5px;
        width: 8px;
        height: 8px;
        margin: auto;
        border-radius: 50%;
        border: 2px solid;
        background-color: #fff;
        color: #d3d3d3;
      }
      .carousel-card {
        box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
        margin-bottom: 10px;
        img {
          display: block;
          width: 100%;
        }
      }
      span {
        display: block;
        margin-bottom: 30px;
      }
      .line {
        width: 110%;
        height: 1px;
        background-color: #d3d3d3;
      }
    }
    .prev,
    .next {
      width: 25px;
      height: 25px;
      position: absolute;
      bottom: 26px;
      background: url("../../assets/img/jpg1.jpg");
      z-index: 1000;
      i {
        display: block;
        width: 100%;
        height: 100%;
        &:hover {
          background-position-x: -25px;
        }
      }
    }
    .prev {
      left: 0;
      i {
        background: url("../../assets/img/prev1.png");
      }
    }
    .next {
      right: 0;
      i {
        background: url("../../assets/img/next1.png");
      }
    }
  }
}
</style>
