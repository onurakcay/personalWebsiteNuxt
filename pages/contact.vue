<script >
import { CLIENT_RENEG_LIMIT } from "tls";
import contactPicture from "../assets/contact.png";
export default {
  data() {
    return {
      title: "Let's get in touch",
      width: 200,
      aspectRatio: 16 / 9,
      contactPic: contactPicture,
      loading: false,

      valid: false,
      firstname: "",
      message: "",
      messageRules: [
        (v) => !!v || "Message is required",
        (v) => v.length >= 10 || "Messsage must be grater than 10 characters",
      ],
      email: "",
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+/.test(v) || "E-mail must be valid",
      ],
    };
  },
  methods: {
    navigate(path) {
      this.$router.push(path);
    },
    submit() {
      const valid = this.$refs.form.validate();
      if (valid) {
        this.loading = true;
      }
    },
  },
};
</script>
<template>
  <div class="contact">
    <div class="wrapper">
      <v-avatar size="100" color="transparent" class="avatar">
        <v-img
          :aspect-ratio="aspectRatio"
          :width="width"
          :src="contactPic"
          cover
        />
      </v-avatar>
      <div class="subTitle">{{ title }}</div>
      <p>You can reach me using following options below.</p>
      <p>Here, check out my social links</p>
      <div class="socials">
        <a href="https://github.com/onurakcay" target="_blank">
          <fa :icon="['fab', 'github']" size="lg" />
        </a>
        <a href="https://www.linkedin.com/in/onurakcaytr/" target="_blank">
          <fa :icon="['fab', 'linkedin-in']" size="lg" />
        </a>
        <a href="mailto:onurakcay.tr@gmail.com">
          <fa :icon="['fas', 'envelope']" size="lg" />
        </a>
      </div>
      <p class="mt-3 mb-1">OR</p>
      <v-row no-gutters>
        <v-col cols="12" sm="12" md="4">
          <v-form ref="form" v-model="valid" lazy-validation class="form">
            <v-container>
              <v-text-field
                v-model="email"
                :rules="emailRules"
                label="E-mail"
                required
                outlined
                :disabled="loading"
              ></v-text-field>
              <v-textarea
                class="mt-2"
                label="Your message..."
                v-model="message"
                :rules="messageRules"
                outlined
                :disabled="loading"
              ></v-textarea>
              <div class="submit">
                <v-btn
                  icon
                  @click="submit"
                  :loading="loading"
                  color="warning"
                  x-large
                >
                  <fa :icon="['fas', 'paper-plane']" />
                </v-btn>
              </div>
            </v-container>
          </v-form>
        </v-col>
      </v-row>
      <p><a href="/about"> Go Back</a></p>
    </div>
  </div>
</template>

<style lang="scss" >
.contact {
  height: 100vh;
  width: 100%;
  align-items: center;
  justify-content: center;
  display: flex;
  .wrapper {
    display: flex;
    width: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    animation: fadeInAnimation ease 3s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
    gap: 0.5rem;
    .row {
      width: 100%;
      justify-content: center;
    }
    .submit {
      display: flex;
      justify-content: center;
      width: 100%;
    }
    .form {
      width: 100%;
    }
    .socials {
      display: flex;
      gap: 0.5rem;
      margin-top: 0.5rem;
      a {
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
    .subTitle {
      font-size: 24px;
      color: #fff;
      font-weight: 100;
      margin-bottom: 0.5rem;
      text-align: center;
    }
    p {
      text-align: center;
      color: #ebebeba3;
      font-size: 1rem;
      a {
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
