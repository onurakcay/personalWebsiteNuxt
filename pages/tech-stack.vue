<script>
import vueLogo from "../assets/techs/vue.png";
import laravelLogo from "../assets/techs/laravel.png";
import awsLogo from "../assets/techs/aws.png";
import flutterLogo from "../assets/techs/flutter.png";
import dockerLogo from "../assets/techs/docker.png";
import drupalLogo from "../assets/techs/drupal.png";
import rabbitLogo from "../assets/techs/rabbit.png";

export default {
  data() {
    return {
      msg: "Hello 🖐️",
      logos: [
        { name: "VueJS", url: vueLogo },
        { name: "Laravel", url: laravelLogo },
        { name: "Flutter", url: flutterLogo },
        { name: "AWS", url: awsLogo },
        { name: "Docker", url: dockerLogo },
        { name: "RabbitMQ", url: rabbitLogo },
        { name: "Drupal", url: drupalLogo },
      ],
      width: 50,
      aspectRatio: 16 / 9,
    };
  },
  methods: {
  
  },
  created() {
    console.log(this.logos[0]);
  },
};
</script>
<template>
  <div class="techStack">
    
    <v-row no-gutters>
      <v-col v-for="(logo, index) in logos" :key="index" cols="12" sm="12" md="3">
        <v-card class="ma-2 pa-2" max-width="344" variant="tonal" :key="item">
          <v-card-item>
            <div>
              <div class="text-h6 mb-1 cardImage">
                <v-img
                  :aspect-ratio="aspectRatio"
                  :width="width"
                  :src="logo.url"
                  contain
                />
              </div>
              <div class="text-h6 mb-1 mt-6 techName">
                {{ logo.name }}
              </div>
            </div>
          </v-card-item>
        </v-card>
      </v-col>
      <a class="closeButton mt-5" href="/about">Go Back</a>

    </v-row>
  </div>
</template>
<style lang="scss" >
.techStack {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  height: 100vh;
  .techName {
    text-align: center;
  }
  .closeButton {
    cursor: pointer;
    text-align: end;
    width: 100%;
    margin-right: 1rem;
    margin-bottom: 1rem;
  }
  .cardImage{
    display: flex;
  }
  a{
    text-align: center;
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
}
</style>
