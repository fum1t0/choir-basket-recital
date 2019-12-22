<template>
  <v-app dark>
    <navibar />
    <v-content>
      <nuxt />
    </v-content>
    <v-footer absolute flat app>
      <span>&copy; 2019</span>
    </v-footer>
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
