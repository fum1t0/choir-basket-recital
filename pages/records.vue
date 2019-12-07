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
      videoInfo: []
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
  async asyncData() {
    const videoInfo = await axios
      .get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          part: 'snippet',
          channelId: 'UCZO1ukfvweX4_kBXd1iP43A',
          key: process.env.API_KEY,
          maxResults: 11
        }
      })
      .then((response) => {
        const filtered_info = response.data.items.filter(function(item) {
          return 'videoId' in item.id
        })
        return filtered_info
      })
    return { videoInfo: videoInfo }
  },
  props: {
    resize: true
  }
}
</script>
<style scoped>
.youtube-videos {
  margin: 0px;
  padding: 0px;
}
</style>
