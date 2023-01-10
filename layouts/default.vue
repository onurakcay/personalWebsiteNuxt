<template>
  <v-app dark>
    <!-- <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title>{{ title }}</v-toolbar-title>
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar> -->
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <!-- <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <!-- <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer> -->
  </v-app>
</template>

<script>
// import { RouterLink, RouterView } from "vue-router";
// import { useRouter } from "vue-router";
export default {
  name: 'DefaultLayout',
  data () {
    return {
      progress: 0,
      pages: ["about", "contact"],
      pageIndex: 0,
      hideProgressBar: false,
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  methods: {
    progressBar() {
      // let currenRoute = this.currentRoute;
      // console.log(currenRoute);

      // if (
      //   this.pageIndex != this.pages.length &&
      //   (currenRoute == undefined || currenRoute == "home")
      // ) {
      //   if (this.progress != 100) {
      //     setTimeout(() => {
      //       this.progress += 10;
      //       this.progressBar();
      //     }, 1000);
      //   } else {
      //     this.$router.push("/" + this.pages[this.pageIndex]);
      //     this.pageIndex += 1;
      //     this.progress = 0;
      //     this.progressBar();
      //   }
      // } else {
      //   this.cancelProgressBar();
      // }
    },
    cancelProgressBar() {
      this.pageIndex = this.pages.length;
      this.hideProgressBar = true;
    },
  },
  created() {
    this.progressBar();

    // console.log("Route Object", currentRoute);
    // addEventListener("click", () => {
    //   this.cancelProgressBar();
    // });
  },
  computed: {
    currentRoute() {
      // const router = useRouter();
      // return this.$router.currentRoute.value.name;
    },
  }

}
</script>
