<template>
  <div class="home">
    <aboutMe :lang="lang" />
    <Skills :lang="lang" />
  </div>
</template>

<script>
import aboutMe from "@/components/Home_comp.vue";
import Skills from "@/components/Skills.vue";
export default {
  props: {
    lang: String
  },
  components: {
    aboutMe,
    Skills
  },
  name: "Home"
};
</script>
