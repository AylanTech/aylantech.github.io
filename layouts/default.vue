<template>
  <v-app :dark="dark" light class="bgPic">
    <app-top-bar :color="color" :dark="dark" :flat="flat"></app-top-bar>
    <v-content>
      <v-container fluid>
        <nuxt />
        <v-btn block @click="changeRTL">
          CHANGE
        </v-btn>
      </v-container>
    </v-content>
    <app-footer :color="color" :fixed="fixed"></app-footer>
  </v-app>
</template>

<script>
import AppFooter from '../components/AppFooter'
import AppTopBar from '../components/AppTopBar'
export default {
  // eslint-disable-next-line vue/no-unused-components
  components: { AppTopBar, AppFooter },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      dark: true,
      flat: true,
      RTL: false,
      lang: 'en',
      color: 'transparent',
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
      title: 'Vuetify.js',
      isMobile: false
    }
  },
  beforeDestroy() {
    if (typeof window !== 'undefined') {
      window.removeEventListener('resize', this.onResize, { passive: true })
    }
  },

  mounted() {
    this.onResize()
    window.addEventListener('resize', this.onResize, { passive: true })
  },

  methods: {
    onResize() {
      this.isMobile = window.innerWidth < 600
    },
    changeRTL() {
      this.RTL = !this.RTL
      this.lang = this.lang === 'en' ? 'fa' : 'en'
      this.$vuetify.rtl = this.RTL
      this.$vuetify.lang.current = this.lang
    }
  }
}
</script>

<style>
body {
  background: url(https://images.pexels.com/photos/186077/pexels-photo-186077.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260)
    no-repeat center center fixed;
  background-size: cover;

  &:after {
    content: '';
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background-color: #1734c1;
    opacity: 0.3;
    z-index: -1;
  }
}
.v-application {
  background: none !important;
}
</style>
