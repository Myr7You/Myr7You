<template>
  <el-header>
    <el-menu
      :default-active="this.$route.path"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
      active-text-color="#ffffff"
      router
    >
      <li class="el-menu-item ">
        <router-link to="/" class="brand"><SVGIMAGE /></router-link>
      </li>
      <li class="el-menu-item float-right hidden-xs-only">
        <el-menu-item v-for="(item, i) in navList" :index="item.name" :key="i">
          {{ item.navItem }}
        </el-menu-item>
        <el-menu-item class="lang-btn">
          <a
            class="lang-btn-en"
            :class="[lang === 'en' ? 'actived' : '']"
            id="en"
            @click="changeLang('en')"
          >
            EN
          </a>
        </el-menu-item>
        <el-menu-item class="lang-btn">
          <a
            class="lang-btn-cn"
            :class="[lang === 'cn' ? 'actived' : '']"
            id="cn"
            @click="changeLang('cn')"
          >
            中
          </a>
        </el-menu-item>
      </li>
      <li class="float-right hidden-sm-and-up">
        <el-menu-item class="lang-btn">
          <a
            class="lang-btn-en"
            :class="[lang === 'en' ? 'actived' : '']"
            id="en"
            @click="changeLang('en')"
          >
            EN
          </a>
        </el-menu-item>
        <el-menu-item class="lang-btn">
          <a
            class="lang-btn-cn"
            :class="[lang === 'cn' ? 'actived' : '']"
            id="cn"
            @click="changeLang('cn')"
          >
            中
          </a>
        </el-menu-item>
        <el-submenu index="1">
          <template slot="title"><i class="el-icon-s-unfold"></i></template>
          <el-menu-item
            v-for="(item, i) in navList"
            :index="item.name"
            :key="i"
          >
            {{ item.navItem }}
          </el-menu-item>
        </el-submenu>
      </li>
    </el-menu>
    <div class="line"></div>
  </el-header>
</template>

<script>
import SVGIMAGE from "@/components/personalLogo.vue";
export default {
  props: {
    lang: String
  },
  components: {
    SVGIMAGE
  },
  data() {
    return {
      navLists: {
        en: [
          { name: "/", navItem: "Home" },
          { name: "/blog", navItem: "Blog" },
          { name: "/about", navItem: "About" }
        ],
        cn: [
          { name: "/", navItem: "主页" },
          { name: "/blog", navItem: "博客" },
          { name: "/about", navItem: "关于" }
        ]
      }
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
    changeLang(id) {
      console.log(id);
      if (this.lang !== id) {
        this.$emit("switch-lang", id);
      }
    }
  },
  computed: {
    navList() {
      if (this.lang === "en") {
        return this.navLists.en;
      } else {
        return this.navLists.cn;
      }
    }
  }
};
</script>

<style scoped></style>
