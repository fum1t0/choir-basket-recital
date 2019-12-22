<template>
  <span>
    <v-navigation-drawer app v-model="drawer"
      >Navigation Lists</v-navigation-drawer
    >
    <v-app-bar :clipped-left="true" fixed app>
      <v-app-bar-nav-icon @click="drawer = !drawer" class="hidden-md-and-up" />
      <v-toolbar-title>
        <router-link to="/" class="toolbar-title">合唱団ばすけ</router-link>
      </v-toolbar-title>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          v-for="page in linked_pages"
          :key="page.link"
          :to="page.link"
          text
          nuxt
          >{{ page.title }}</v-btn
        >
      </v-toolbar-items>
    </v-app-bar>
  </span>
</template>

<script>
export default {
  data() {
    return {
      linked_pages: [
        { title: '合唱団ばすけとは', link: '/about-basket' },
        { title: '演奏会のご案内', link: '/recital' },
        { title: '過去の演奏', link: '/records' }
      ],
      drawer: null
    }
  }
}
</script>

<style scoped>
.toolbar-title {
  color: black;
  text-decoration: none;
  padding-left: 0%;
}
</style>
