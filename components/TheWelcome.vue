
<script>
import profile from "../assets/profile.png";
export default {
  data() {
    return {
      msg: "Hello 🖐️",
      name: "Welcome to my personal Web Page",
      width: 200,
      aspectRatio: 16 / 9,
      profile: profile,
      loading: false,
    };
  },
};
</script>

<template>
  <div class="greetings">
    <v-avatar size="100" color="transparent" class="avatar">
      <v-img :aspect-ratio="aspectRatio" :width="width" :src="profile" cover />
    </v-avatar>
    <div class="helloText">{{ msg }}</div>
    <div class="subTitle">{{ name }}</div>
    <v-btn
      @click="loading = true"
      :loading="loading"
      text
      class="link mt-3"
      color="warning"
      to="/about"
    >
      Who am i?
    </v-btn>
  </div>
</template>

<style lang="scss" scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}
.greetings {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.helloText {
  font-size: 48px;
  font-weight: bold;
}
.subTitle {
  font-size: 24px;
  font-weight: 100;
  text-align: center;
}
.link {
  font-size: 1rem;
  font-weight: bold;
  text-align: center;
}
</style>
