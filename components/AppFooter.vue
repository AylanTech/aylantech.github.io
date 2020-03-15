<template>
  <v-footer :color="color" :fixed="fixed" padless app>
    <v-layout row align-center justify-center>
      <v-card :color="color" flat tile class="text-center">
        <v-card-text class="overline">
          &copy; {{ new Date().getFullYear() }} — <strong>Aylan Dance</strong>
        </v-card-text>
      </v-card>
    </v-layout>
  </v-footer>
</template>

<script>
export default {
  name: 'AppFooter',
  props: {
    color: {
      type: String,
      default: 'transparent'
    },
    fixed: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped></style>
