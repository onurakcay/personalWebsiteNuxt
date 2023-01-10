<script >
import aboutPicture from "../assets/about.png";
export default {
  data() {
    return {
      msg: "Hello 🖐️",
      name: "My Name is Onur AKÇAY",
      width: 200,
      aspectRatio: 16 / 9,
      aboutPic: aboutPicture,
      loading: false,
    };
  },
  methods: {
    navigate(path) {
      this.$router.push(path);
    },
  },
};
</script>
<template>
  <div class="about">
    <v-avatar size="100" color="transparent" class="avatar">
      <v-img :aspect-ratio="aspectRatio" :width="width" :src="aboutPic" cover />
    </v-avatar>
    <div class="subTitle">{{ name }}</div>
    <p>
      I love to solve complicated problems and use up-to-date technologies while
      doing that.
    </p>
    <p>
      Here, check out my

      <a class="link" href="/tech-stack"> tech stack </a>,
      <v-tooltip top>
        <template v-slot:activator="{ on, attrs }">
          <a v-bind="attrs" v-on="on" class="disabled-link"> projects </a>
        </template>
        <span>Coming Soon</span>
      </v-tooltip>
      and also
      <v-tooltip top>
        <template v-slot:activator="{ on, attrs }">
          <a v-bind="attrs" v-on="on" class="disabled-link"> blogs </a>
        </template>
        <span>Coming Soon</span>
      </v-tooltip>
    </p>

    <v-btn
      @click="loading = true"
      text
      class="link mt-2"
      color="warning"
      to="/contact"
      :loading="loading"
    >
      Contact
    </v-btn>
  </div>
</template>

<style lang="scss" >
.about {
  display: flex;
  height: 100vh;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  animation: fadeInAnimation ease 3s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  gap: 0.5rem;
  .subTitle {
    font-size: 24px;
    color: #fff;
    font-weight: 100;
    margin-bottom: 0.5rem;
  }
  p {
    text-align: center;

    color: #ebebeba3;
    font-size: 1rem;
    .link {
      background: transparent;
      border: none;
      border-radius: 0;
      text-decoration: underline;
      color: #ffd333;
      transition: 0.4s;
      padding: 0 4px;
      border-radius: 4px;
      cursor: pointer;
    }
    .disabled-link {
      background: transparent;
      border: none;
      border-radius: 0;
      text-decoration: underline;
      color: #ebebeba3;
      transition: 0.4s;
      padding: 0 4px;
      border-radius: 4px;
      cursor: not-allowed;
    }
  }
}
@keyframes fadeInAnimation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
