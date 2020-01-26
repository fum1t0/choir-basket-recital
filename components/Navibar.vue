<template>
  <span>
    <v-bottom-navigation
      app
      dark
      class="hidden-md-and-up"
      color="#FAFAFA"
      background-color="#CC4116"
    >
      <v-btn
        width="80px"
        height="56px"
        v-for="page in linked_pages"
        :key="page.link"
        nuxt
        :to="page.link"
      >
        <span>{{ page.title.sp }}</span>
        <v-icon>{{ page.icon }}</v-icon>
      </v-btn>
    </v-bottom-navigation>
    <v-app-bar dark clipped-left fixed app color="#CC4116">
      <v-toolbar-title>
        <nuxt-link to="/" class="toolbar-title">合唱団ばすけ</nuxt-link>
      </v-toolbar-title>
      <div class="hidden-sm-and-down">
        <v-btn
          v-for="page in linked_pages"
          dark
          :key="page.link"
          :to="page.link"
          text
          nuxt
          large
          rounded
          class="toolbar-title"
          color="#FAFAFA"
          >{{ page.title.pc }}</v-btn
        >
      </div>
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
          link: '/',
          icon: 'mdi-basketball'
        },
        {
          title: { pc: '演奏会のご案内', sp: 'concert' },
          link: '/concert',
          icon: 'mdi-music-clef-treble'
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
  color: #fafafa;
  font-weight: 400;
  text-decoration: none;
  padding-left: 0%;
  padding-right: 1em;
}
.drawer-icon {
  margin-right: 1em;
}
</style>
