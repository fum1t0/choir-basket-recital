/* eslint-disable prettier/prettier */
<template>
  <v-layout>
    <v-flex class="text-center">
      <img src="/v.png" alt="Vuetify.js" class="mb-5" />
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
        </footer>
      </blockquote>
      <youtube
        v-for="videoID in videoIDs"
        v-bind:key="videoID"
        :video-id="videoID"
        ref="youtube"
      ></youtube>
    </v-flex>
  </v-layout>
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
      videoIDs: [],
      resp: null,
      apiKey: 'AIzaSyD7DsIYDle6E2Jaei0dbG4WWOgEcG6wMi4',
      channelID: 'UCZO1ukfvweX4_kBXd1iP43A',
      maxItems: 5
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
          key: this.apiKey,
          maxResults: this.maxItems
        }
      })
      .then((response) => {
        const videosInfo = response.items.filter(function(item) {
          return 'videoId' in item.id
        })
        this.videoIDs = videosInfo.map(function(info) {
          return info.id.videoId
        })
      })
  }
}
</script>
