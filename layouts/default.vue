<template>
  <v-app dark>
    <Navibar />
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
import Navibar from '@/components/Navibar'

export default {
  components: {
    Navibar
  }
}
</script>

<style>
body {
  background: #ff3d00;
}
.v-application {
  font-family: 'M PLUS Rounded 1c';
}
.v-application.theme--dark {
  background-color: #ff3d00;
  color: #fafafa;
}
</style>
