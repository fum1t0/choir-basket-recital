<template>
  <div>
    <v-row align="start" justify="center">
      <v-img src="IMG_1446.jpg">
        <v-container>
          <v-row align="center" justify="center">
            <v-col cols="12">
              <div class="title">HogeFugaPiyo</div>
            </v-col>
          </v-row>
        </v-container>
      </v-img>
    </v-row>
    <v-container>
      <v-row>
        <v-col
          v-for="info in videoInfo"
          v-bind:key="info.id.videoId"
          xl="4"
          lg="6"
          md="6"
          cols="12"
        >
          <div>
            <youtube
              :video-id="info.id.videoId"
              ref="youtube"
              fitParent
            ></youtube>
          </div>
        </v-col>
      </v-row>
    </v-container>
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
.title {
  text-align: center;
  color: #fcfcfc;
  margin-top: 50%;
  margin-bottom: 50%;
}
</style>
