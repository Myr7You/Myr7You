<template>
  <div id="app">
    <Nav :lang="lang" @switch-lang="switchLang" />
    <router-view :lang="lang" />
  </div>
</template>

<script>
import Nav from "@/components/Nav.vue";
export default {
  components: {
    Nav
  },
  data() {
    return {
      lang: "en"
    };
  },
  methods: {
    switchLang(id) {
      console.log(id);
      if (this.lang !== id) {
        this.lang = id;
      }
      console.log(this.lang);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
html {
  -webkit-text-size-adjust: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 18px;
}

body {
  margin: 0;
  padding: 0;
  font-family: "Open Sans", sans-serif;
  font-size: 18px;
  line-height: 1.5;
}
#app {
  height: 100vh;
}
hr {
  box-sizing: content-box;
  height: 0;
  overflow: visible;
}
a {
  color: #000;
  font-weight: 600;
  text-decoration: none;
  -webkit-transition: color 0.3s ease;
  -o-transition: color 0.3s linear;
  -ms-transition: color 0.3s ease;
  -moz-transition: color 0s ease;
  transition: color 0.6s ease;
}
a:hover {
  background: transparent;
  color: #fff;
}
.router-link-exact-active {
  color: #fff;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  display: block;
  align-items: center;
  font-family: "Montserrat", sans-serif;
}
/* Type will scale with document */
h1 {
  font-size: 3rem;
}
h2 {
  font-size: 2.5rem;
}
h3 {
  font-size: 2rem;
}
h4 {
  font-size: 1.5rem;
  margin: 0;
}
p {
  display: block;
  font-size: 1.4rem;
  margin: 0;
}
/* Modules will scale with document */
.header {
  font-size: 1.5rem;
}
.footer {
  font-size: 0.75rem;
}
.sidebar {
  font-size: 0.85rem;
}

/* element menu  */
.el-header {
  padding: 0 !important;
}
.el-header ul {
  padding: 0 20px;
}
.el-menu {
  background: linear-gradient(to right, #16c0b0, #84cf6a);
}

.el-menu .float-right {
  float: right !important;
}
.el-menu .float-right:last-child {
  margin-right: 1.2rem;
}
.el-menu .float-right li {
  float: left;
}

.el-menu .el-menu-item,
.el-submenu .el-submenu__title {
  font-size: 1em;
  font-weight: 600;
}
.el-menu-item:hover,
.el-menu-item:focus,
.el-submenu__title:hover,
.el-submenu__title:focus {
  background: none !important;
  color: #fff !important;
}

.lang-btn {
  padding-right: 0 !important;
}
.lang-btn .actived {
  color: #fff !important;
}
.lang-btn:last-child {
  padding-left: 0 !important;
}
.lang-btn-en:after {
  margin-right: 5px;
  content: "/";
  color: #000;
}
.el-submenu__title i {
  right: 0px;
  font-size: 0.8em;
  font-weight: bold;
  color: #000 !important;
}
.el-submenu__title:hover i {
  right: 0px;
  font-size: 0.8em;
  font-weight: bold;
  color: #fff !important;
}

.el-menu--popup .is-active {
  background: linear-gradient(to right, #16c0b0, #84cf6a);
}
@media (max-width: 1280px) {
  html {
    font-size: 18px;
  }
  p {
    font-size: 0.9rem;
  }
}
@media (max-width: 1024px) {
  html {
    font-size: 14px;
  }
  p {
    font-size: 1.2rem;
  }
}
@media (max-width: 768px) {
  html {
    font-size: 12px;
  }
  .el-header ul {
    padding: 0;
  }
  .el-submenu__title i {
    font-size: 2em !important;
    font-weight: bold;
    color: #fff !important;
  }
  .el-submenu .el-submenu__icon-arrow {
    display: none;
  }
  .lang-btn {
    padding: 0 !important;
  }
  .sm-none {
    display: none;
  }
}
@media (max-width: 450px) {
  html {
    font-size: 10px;
  }
  .sm-none {
    display: none;
  }
}
@media (max-width: 320px) {
  html {
    font-size: 8px;
  }
}
</style>
