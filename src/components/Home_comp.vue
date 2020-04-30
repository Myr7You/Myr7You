<template>
  <div class="background-div">
    <el-row type="flex" justify="center" class="skewDiv">
      <el-col :md="12" :sm="24">
        <div class="skewDiv_content" v-show="$attrs.lang === 'en'">
          <h1>Hello ~</h1>
          <h1>I am Myrs You.</h1>
          <h2>I build stuff for the web</h2>
          <br />
          <br class="sm-none" />
          <p>
            I'm a front-end web developerbased in Shenzhen,China
            <br />
            I build outstanding, high-quality websites and web applications.
            <br />
            <br class="sm-none" />
            Scroll down to find out more about my work or hire me.
          </p>
        </div>
        <div class="skewDiv_content" v-show="$attrs.lang === 'cn'">
          <h1>嗨 ~</h1>
          <h1>我是游竣平.</h1>
          <h2>是一位前端工程师</h2>
          <br />
          <br class="sm-none" />
          <p>
            我是在深圳生活的前端工程师
            <br />
            会设计和搭建现代响应式的网页应用程序
            <br />
            <br class="sm-none" />
            下滑了解更多关于我的工作吧！
          </p>
        </div>
      </el-col>
      <el-col :md="12" class="hidden-sm-and-down">
        <div class="skew">
          <el-image class="imgDiv" :src="images.url"> </el-image>
        </div>
      </el-col>
      <div class="overlay"></div>
    </el-row>
    <div class="top-overlay"></div>
    <i class="el-icon-arrow-down"></i>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: {
        url: require("@/assets/IMG_3671.jpg")
      }
    };
  },
  name: "Home"
};
</script>

<style scoped>
h1,
h3,
p {
  margin-top: 0;
  color: rgb(255, 255, 255);
  text-align: left;
  line-height: normal;
  margin-bottom: 0;
  width: 75%;
}

h2 {
  margin-top: 0;
  color: rgb(218, 170, 13);
  text-align: left;
  line-height: normal;
  margin-bottom: 0;
}

.background-div {
  height: calc(100vh - 60px);
  background: url("~@/assets/123.jpg") no-repeat center center fixed;
  background-size: 120% auto;
  background-position: 90% 10%;
  position: relative;
  z-index: 0;
  overflow: hidden;
}
.skewDiv {
  z-index: 100;
  height: 75vh;
  overflow: hidden;
  transform: rotate(-5deg) skew(-5deg) translateY(8.5vh);
  position: relative;
}
.overlay {
  z-index: 100;
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, #4ac29a 5%, #000 20% 60%, #f2c94c 90%);
  opacity: 0.5;
  position: absolute;
  right: 0%;
  top: 0;
  transform: skew(0deg);
}
.top-overlay {
  z-index: 1;
  width: 100%;
  height: 100%;
  background: linear-gradient(-20deg, #000, #16c0b0);
  opacity: 0.7;
  position: absolute;
  left: 0%;
  top: 0;
}

.skewDiv_content {
  z-index: 1000;
  position: relative;
  opacity: 0;
  animation: textSlide 1s ease-out forwards 0.1s;
  width: 100%;
}
.skew {
  z-index: 100;
  width: 55%;
  height: 80vh;
  position: absolute;
  right: 100%;
  animation: imageSlide 1s ease-out forwards 0.5s;
}
.imgDiv {
  position: relative;
  top: 50%;
  z-index: 10;
  width: 90%;
  transform: skew(0) translateY(-57%);
  /* transform: rotate(5deg) skew(5deg) translateY(8.5vh); */
}
i.el-icon-arrow-down {
  opacity: 0;
  position: absolute;
  left: 50%;
  bottom: 5%;
  transform: translateX(-50%);
  z-index: 10000;
  font-size: 3rem;
  font-weight: bold;
  color: #fff;
  animation: drop 1s infinite 3s;
}

@keyframes drop {
  0% {
    opacity: 1;
    bottom: 5%;
  }
  50% {
    opacity: 0.5;
    bottom: 6%;
  }
  100% {
    opacity: 1;
    bottom: 5%;
  }
}
@keyframes imageSlide {
  from {
    right: 100%;
  }

  to {
    right: -5%;
  }
}

@keyframes textSlide {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
@media screen and (max-width: 320px) {
  .background-div {
    height: calc(70vh - 60px);
    background-position: 90% 10%;
  }
  .skewDiv {
    height: 60vh;
    transform: none;
  }
  .skewDiv_content {
    width: 100%;
    left: 50%;
    top: 50%;
    transform: translate(-40%, -52%);
  }
}
@media screen and (min-width: 321px) and (max-width: 450px) {
  .background-div {
    height: calc(60vh - 60px);
    background-position: 90% 10%;
  }
  .skewDiv {
    height: 55vh;
    transform: none;
  }
  .skewDiv_content {
    width: 100%;
    left: 50%;
    top: 50%;
    transform: translate(-40%, -54%);
  }
}
@media screen and (min-width: 451px) and (max-width: 768px) {
  .background-div {
    height: calc(48vh - 60px);
  }
  .skewDiv {
    height: 30vh;
    transform: rotate(-5deg) skew(-5deg) translateY(4vh);
  }
  .skewDiv_content {
    left: 50%;
    top: 50%;
    transform: skew(5deg) translateY(-50%) translateX(-35%);
  }
  .imgDiv {
    top: 20%;
    transform: skew(0) translateY(-57%);
  }
}
@media screen and (min-width: 769px) and (max-width: 1024px) {
  .background-div {
    height: calc(52vh - 60px);
  }
  .skewDiv {
    height: 35vh;
    transform: rotate(-5deg) skew(-5deg) translateY(4.5vh);
  }
  .skewDiv_content {
    left: 50%;
    top: 50%;
    transform: skew(5deg) translateY(-50%) translateX(-30%);
  }
  .imgDiv {
    top: 25%;
    transform: skew(0) translateY(-57%);
  }
}
@media screen and (min-width: 1025px) and (max-width: 1279px) {
  .background-div {
    height: calc(80vh - 60px);
  }
  .skewDiv {
    height: 55vh;
    transform: rotate(-5deg) skew(-5deg) translateY(6vh);
  }
  .skewDiv_content {
    left: 50%;
    top: 48%;
    transform: skew(5deg) translateY(-50%) translateX(-38%);
  }
  .imgDiv {
    top: 34%;
    transform: skew(0) translateY(-50%);
  }
}
@media screen and (min-width: 1280px) {
  .background-div {
    height: calc(100vh - 60px);
  }
  .skewDiv {
    height: 75vh;
    transform: rotate(-5deg) skew(-5deg) translateY(9vh);
  }
  .skewDiv_content {
    left: 50%;
    top: 50%;
    transform: skew(5deg) translateY(-50%) translateX(-30%);
  }
  .imgDiv {
    top: 50%;
    transform: skew(0) translateY(-57%);
  }
}
</style>
