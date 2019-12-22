<template>
  <span>
    <v-bottom-navigation
      app
      class="hidden-md-and-up"
      color="#F54E1B"
      background-color="#FAFAFA"
    >
      <v-btn v-for="page in linked_pages" :key="page.link" nuxt :to="page.link">
        <span>{{ page.title.sp }}</span>
        <v-icon>{{ page.icon }}</v-icon>
      </v-btn>
    </v-bottom-navigation>
    <v-app-bar clipped-left fixed app color="#FAFAFA">
      <v-toolbar-title>
        <nuxt-link to="/" class="toolbar-title" color="#000000"
          >合唱団ばすけ</nuxt-link
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
          class="toolbar-title"
          color="#000000"
          >{{ page.title.pc }}</v-btn
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
          title: { pc: '合唱団ばすけとは', sp: 'about' },
          link: '/about-basket',
          icon: 'mdi-basketball'
        },
        {
          title: { pc: '演奏会のご案内', sp: 'info' },
          link: '/recital',
          icon: 'mdi-information-variant'
        },
        {
          title: { pc: '過去の演奏', sp: 'records' },
          link: '/records',
          icon: 'mdi-youtube'
        }
      ],
      drawer: null
    }
  }
}
</script>

<style scoped>
.toolbar-title {
  color: #000000;
  font-weight: 400;
  text-decoration: none;
  padding-left: 0%;
  padding-right: 1em;
}
.drawer-icon {
  margin-right: 1em;
}
</style>
