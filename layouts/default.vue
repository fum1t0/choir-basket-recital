<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title>
        <router-link to="/" class="toolbar-title">{{ title }}</router-link>
      </v-toolbar-title>
      <v-toolbar-items>
        <v-btn text to="/about-basket" nuxt>合唱団ばすけとは</v-btn>
        <v-btn text to="/recital" nuxt>演奏会のご案内</v-btn>
        <v-btn text to="/records" nuxt>過去の演奏</v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
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
      title: '合唱団ばすけ'
    }
  }
}
</script>

<style scoped>
.toolbar-title {
  color: black;
  text-decoration: none;
}
</style>
