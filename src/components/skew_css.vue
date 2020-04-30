<template>
  <div class="background-div">
    <el-row type="flex" justify="end" class="about">
      <el-col :span="12" :sm="24">
        <div class="about_content">
          <p>Hello! My name is</p>
          <h1>Myrs You.</h1>
          <p>
            I am trying to make a punk-rock design,rotated areas are really cool
            and you'll look hip and cool
          </p>
        </div>
      </el-col>
      <el-col :span="12" class="hidden-sm-and-down">
        <div class="skew">
          <el-image class="imgDiv" :src="images.url"> </el-image>
        </div>
      </el-col>
      <div class="overlay"></div>
    </el-row>
    <div class="top-overlay"></div>
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
  name: "About"
};
</script>

<style scoped>
h1,
p {
  margin-top: 0;
  color: white;
  text-align: left;
  line-height: normal;
}
p {
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
.about {
  z-index: 100;
  height: 75vh;
  overflow: hidden;
  transform: rotate(-5deg) skew(-5deg) translateY(8.5vh);
  position: relative;
}

/* .about > * {
  transform: skew(5deg);
} */

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

.about_content {
  z-index: 1000;
  position: relative;
  left: 100%;
  animation: textSlide 1s ease-out forwards 0.5s;
  transform: skew(5deg) translateY(10vh);
  width: 70%;
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
    left: 100%;
  }

  to {
    left: 10%;
  }
}

@media screen and (max-width: 767px) {
  .background-div {
    height: calc(48vh - 60px);
  }
  .about {
    height: 30vh;
    transform: rotate(-5deg) skew(-5deg) translateY(4vh);
  }
  .about_content {
    transform: skew(5deg) translateY(5vh);
  }
  .imgDiv {
    top: 20%;
    transform: skew(0) translateY(-57%);
  }
}
@media screen and (min-width: 768px) and (max-width: 1024px) {
  .background-div {
    height: calc(52vh - 60px);
  }
  .about {
    height: 35vh;
    transform: rotate(-5deg) skew(-5deg) translateY(4.5vh);
  }
  .about_content {
    transform: skew(5deg) translateY(5vh);
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
  .about {
    height: 55vh;
    transform: rotate(-5deg) skew(-5deg) translateY(6vh);
  }
  .about_content {
    transform: skew(5deg) translateY(6vh);
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
  .about {
    height: 75vh;
    transform: rotate(-5deg) skew(-5deg) translateY(9vh);
  }
  .about_content {
    transform: skew(5deg) translateY(10vh);
  }
  .imgDiv {
    top: 50%;
    transform: skew(0) translateY(-57%);
  }
}
/* section {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 1000px;
  background-color: #333;
  display: flex;
}
.content-div {
  width: 60%;
  background-color: rgb(27, 88, 85);
  height: 100%;
  box-sizing: border-box;
}
.img-div {
  width: 40%;
  height: 100%;
  background: rgb(26, 197, 55);
  box-sizing: border-box;
  border-left: 100px solid rgb(27, 88, 85);
  border-bottom: 1000px solid transparent;
  background: url("~@/assets/IMG_3140.jpg") no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: 40% auto;
  background-position: 100% 7%;
}
.color-overlay {
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, #4ac29a, #f2c94c);
  opacity: 0.3;
  position: absolute;
  left: 0%;
} */
</style>
