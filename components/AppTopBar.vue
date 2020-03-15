<template>
  <v-app-bar :color="color" :dark="dark" :light="!dark" :flat="flat" app>
    <v-layout row align-center justify-space-between>
      <v-flex shrink>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      </v-flex>
      <v-flex shrink>
        <v-toolbar-title>
          <v-avatar :size="25">
            <img alt="Aylan Dnace" src="/v.png" />
          </v-avatar>
        </v-toolbar-title>
      </v-flex>
      <v-flex shrink class="d-none d-sm-flex">
        <v-btn icon large>
          <v-icon>mdi-facebook</v-icon>
        </v-btn>
        <v-btn icon large>
          <v-icon>mdi-instagram</v-icon>
        </v-btn>
        <v-btn icon large>
          <v-icon>mdi-twitter</v-icon>
        </v-btn>
      </v-flex>
    </v-layout>
  </v-app-bar>
</template>

<script>
export default {
  name: 'AppTopBar',
  props: {
    color: {
      type: String,
      default: 'transparent'
    },
    dark: {
      type: Boolean,
      default: false
    },
    flat: {
      type: Boolean,
      default: true
    },
    title: {
      type: String,
      default: 'Aylan'
    }
  },
  data() {
    return {
      drawer: false,
      miniVariant: false,
      clipped: false
    }
  }
}
</script>

<style scoped></style>
