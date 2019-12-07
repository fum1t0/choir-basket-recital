<template>
  <div>
    <v-card color="orange darken-3" class="title">
      <v-card-title primary-title class="white--text">過去の演奏</v-card-title>
    </v-card>
    <v-row>
      <v-col v-for="info in videoInfo" v-bind:key="info.id.videoId" cols="6">
        <div class="youtube-videos">
          <youtube
            :video-id="info.id.videoId"
            ref="youtube"
            fitParent
          ></youtube>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueYoutube from 'vue-youtube'

Vue.use(VueYoutube)
Vue.use(axios)
export default {
  head() {
    return { title: '過去の演奏' }
  },
  data() {
    return {
      videoInfo: [],
      channelID: 'UCZO1ukfvweX4_kBXd1iP43A',
      maxItems: 9
    }
  },
  methods: {
    playVideo() {
      this.player.playVideo()
    }
  },
  computed: {
    player() {
      return this.$refs.youtube.player
    }
  },
  created: function() {
    this.$axios
      .$get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          part: 'snippet',
          channelId: this.channelID,
          key: process.env.API_KEY,
          maxResults: this.maxItems
        }
      })
      .then((response) => {
        this.videoInfo = response.items.filter(function(item) {
          return 'videoId' in item.id
        })
      })
  },
  props: {
    resize: true
  }
}
</script>
<style scoped>
.youtube-videos {
  margin: 10px;
  padding: 5px;
}
</style>
