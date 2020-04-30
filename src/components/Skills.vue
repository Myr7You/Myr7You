<template>
  <el-container class="skills">
    <el-header> </el-header>
    <el-main v-if="skills && lang === 'en'">
      <el-row type="flex" justify="center" class="skill_header">
        <el-col :span="24">
          <h1>Skills</h1>
          <p class="sub_title">
            These are the following skills I have aquired through hard work on
            my personal life.
          </p>
        </el-col>
      </el-row>
      <el-row class="row-bg" :gutter="20">
        <el-col
          :xs="24"
          :sm="8"
          :md="8"
          :lg="8"
          :xl="8"
          v-for="(skill, index) in skills.en"
          :key="index"
        >
          <div class="grid-content">
            <BaseIcon
              :name="skill.icon"
              width="[ skill.iconW ? {skill.iconW | 100}]"
            ></BaseIcon>
            <h4>{{ skill.title }}</h4>
            <p v-html="skill.content"></p>
          </div>
        </el-col>
      </el-row>
      <!-- <el-row
        type="flex"
        class="row-bg"
        justify="space-around"
        v-for="(i, index) in Math.ceil(skills.en.length / 3)"
        :key="index"
      >
        <el-col
          :sm="8"
          v-for="(skill, index) in skills.en.slice((i - 1) * 3, i * 3)"
          :key="index"
        >
          <div class="grid-content">
            <BaseIcon
              :name="skill.icon"
              width="[ skill.iconW ? {skill.iconW |''}]"
            ></BaseIcon>
            <h4>{{ skill.title }}</h4>
            <p v-html="skill.content"></p>
          </div>
        </el-col>
      </el-row> -->
    </el-main>
    <el-main v-if="skills && lang === 'cn'">
      <el-row type="flex" justify="center" class="skill_header">
        <el-col :span="24">
          <h1>技能</h1>
          <p class="sub_title">
            以下是个人通过不断学习和工作生活中掌握的技能
          </p>
        </el-col>
      </el-row>
      <el-row class="row-bg" :gutter="20">
        <el-col
          :xs="24"
          :sm="8"
          :md="8"
          :lg="8"
          :xl="8"
          v-for="(skill, index) in skills.cn"
          :key="index"
        >
          <div class="grid-content">
            <BaseIcon
              :name="skill.icon"
              width="[ skill.iconW ? {skill.iconW | 100}]"
            ></BaseIcon>
            <h4>{{ skill.title }}</h4>
            <p v-html="skill.content"></p>
          </div>
        </el-col>
      </el-row>
      <!-- <el-row
        type="flex"
        class="row-bg"
        justify="space-around"
        v-for="(i, index) in Math.ceil(skills.cn.length / 3)"
        :key="index"
      >
        <el-col
          :sm="8"
          v-for="(skill, index) in skills.cn.slice((i - 1) * 3, i * 3)"
          :key="index"
        >
          <div class="grid-content">
            <BaseIcon
              :name="skill.icon"
              width="[ skill.iconW ? {skill.iconW |''}]"
            ></BaseIcon>
            <h4>{{ skill.title }}</h4>
            <p v-html="skill.content"></p>
          </div>
        </el-col>
      </el-row> -->
    </el-main>
  </el-container>
</template>

<script>
import BaseIcon from "@/components/BaseIcon.vue";
export default {
  props: {
    lang: String
  },
  components: {
    BaseIcon
  },
  data() {
    return {
      skills: {
        en: [
          {
            icon: "chrome",
            iconW: 160,
            title: "Web Oriented",
            content:
              "Experience developing web applications on modern platforms as afont-end developer using HTML5, CSS3, Javascript.<br /> Willing to learn more about back-end skills and amid to be a full stack developer in the future."
          },
          {
            icon: "code",
            title: "Multi-Coding-Skill",
            content:
              "Experience with HTML5, CSS3, SCSS, Bootstrap,Javascript(ES6 and beyond), Git. Good at VUE(Vue Cli, Vue Router, Vuex, Nuxt.js).<br /> Know about React.js, SQL, Ruby, Rails, Node.js and willing to learn more."
          },
          {
            icon: "lang",
            title: "Multi-language",
            content:
              "Mother language Chinese are Mandarin and Cantonese.Also good at English. Reading english document and Communication. <br /> Experience utilizing Google and stack overflow to solve the problem."
          },
          {
            icon: "fire",
            title: "Learning by Doing",
            content:
              "Experience being a motivated learner working on projects or playing around with existing code bases."
          },
          {
            icon: "design",
            title: "Design",
            content:
              "Experience with Adobe Photoshop, Illustrator and Rhino modeling. Interested in UI Design, layout and CSS Animations."
          },
          {
            icon: "team",
            iconW: 160,
            title: "Team Cooperation",
            content:
              "Experience working in team.Maintain good communication with other team members, and are willing to learn from others."
          }
        ],
        cn: [
          {
            icon: "chrome",
            iconW: 160,
            title: "面向网络",
            content:
              "作为前端工程师具备有HTML5，CSS3，Javascript等现代网页开发应用程序的使用经验。还保持着不断学习新的前端和后端知识，目标是未来成为一个全栈工程师"
          },
          {
            icon: "code",
            title: "多种编程技能",
            content:
              "熟练使用HTML5，CSS3，SCSS，Bootstrap，Javascript（ES6及更高版本），Git等。会VUE全家桶使用（该个人网页就是使用VUE搭建的）<br /> 还有了解不继续学习React.js,Node.js,SQL,Ruby on Rails等技术"
          },
          {
            icon: "lang",
            title: "多语言技能",
            content:
              "母语中文普通话和粤语.还擅长英语. 可以无障碍阅读英文技术文档和进行简单的交流. <br /> 熟练的使用Google和stack overflow等平台来解决开放中碰到的技术问题."
          },
          {
            icon: "fire",
            title: "实践学习",
            content:
              "是一位积极的学习者，在不断的尝试和使用各种资料库并合理的运用于项目之中"
          },
          {
            icon: "design",
            title: "设计能力",
            content:
              "熟练的使用Adobe Photoshop, Illustrator 和 Rhino 建模等设计软件.<br /> 对UI设计感兴趣, 且注重排版和CSS动画. （该个人网页也是自己设计的）"
          },
          {
            icon: "team",
            iconW: 160,
            title: "团队合作",
            content:
              "有很好的团队合作经验.与团队成员有良好的沟通与交流,愿意向他人学习."
          }
        ]
      }
    };
  }
};
</script>

<style scoped>
.el-header {
  height: 0 !important;
}
h1 {
  margin-bottom: 1rem;
}

.sub_title {
  font-size: 1.2rem;
  margin-bottom: 3rem;
}
h4 {
  margin: 0 auto;
}
p {
  margin: 0 auto;
}
@media screen and (max-width: 765px) {
  .el-col {
    margin-bottom: 50px;
  }
}
@media screen and (min-width: 768px) {
  .grid-content {
    margin: 0 auto;
    height: 350px;
  }
}
@media screen and (min-width: 1280px) {
  p {
    margin: 0 20px 40px;
    font-size: 0.85rem;
  }
}
</style>
