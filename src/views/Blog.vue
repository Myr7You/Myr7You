<template>
  <section class="blog">
    <div class="blog_content">
      <h1>Coming soon ...</h1>
    </div>
    <div class="overlay"></div>
  </section>
</template>

<script>
export default { name: "Blog" };
</script>

<style scoped>
h1 {
  position: relative;
  top: 10%;
  background: url("~@/assets/123.jpg") no-repeat center center fixed;
  font-size: 200px;
  font-weight: bolder;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.blog_content {
  position: absolute;
  width: calc(100% - 40px);
  height: calc(100vh - 100px);
  z-index: 1000;
  margin: 20px;
  opacity: 0.7;
  background: linear-gradient(to bottom, #fff, #000 35% 65%, #fff);
}
.overlay {
  z-index: 100;
  position: absolute;
  width: 100%;
  height: calc(100vh - 60px);
  background: url("~@/assets/123.jpg") no-repeat center center fixed;
}
</style>
