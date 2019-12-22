<template>
  <span>
    <v-navigation-drawer
      app
      temporary
      clipped
      v-model="drawer"
      class="hidden-md-and-up grey lighten-5"
      ><v-list>
        <v-list-item nuxt to="/">
          <v-list-item-content>
            <v-list-item-title class="font-weight-bold">
              <v-icon class="drawer-icon">mdi-home</v-icon>
              ホーム
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item
          v-for="page in linked_pages"
          :key="page.link"
          nuxt
          :to="page.link"
        >
          <v-list-item-content>
            <v-list-item-title class="font-weight-bold"
              ><v-icon class="drawer-icon">{{ page.icon }}</v-icon
              >{{ page.title }}</v-list-item-title
            >
          </v-list-item-content>
        </v-list-item>
      </v-list></v-navigation-drawer
    >
    <v-app-bar clipped-left fixed app class="orange darken-3">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        class="hidden-md-and-up"
        color="grey lighten-5"
      />
      <v-toolbar-title>
        <router-link to="/" class="toolbar-title grey--text text--lighten-5"
          >合唱団ばすけ</router-link
        >
      </v-toolbar-title>
      <v-app-bar-items class="hidden-sm-and-down">
        <v-btn
          v-for="page in linked_pages"
          :key="page.link"
          :to="page.link"
          text
          nuxt
          large
          rounded
          class="toolbar-title grey--text text--lighten-5"
          >{{ page.title }}</v-btn
        >
      </v-app-bar-items>
    </v-app-bar>
  </span>
</template>

<script>
export default {
  data() {
    return {
      main_icon: 'mdi-basketball',
      linked_pages: [
        {
          title: '合唱団ばすけとは',
          link: '/about-basket',
          icon: 'mdi-basketball'
        },
        {
          title: '演奏会のご案内',
          link: '/recital',
          icon: 'mdi-information-variant'
        },
        { title: '過去の演奏', link: '/records', icon: 'mdi-youtube' }
      ],
      drawer: null
    }
  }
}
</script>

<style scoped>
.toolbar-title {
  text-decoration: none;
  padding-left: 0%;
  padding-right: 1em;
}
.drawer-icon {
  margin-right: 1em;
}
</style>
