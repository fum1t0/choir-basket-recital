<template>
  <div>
    <v-container fluid>
      <v-img src="IMG_1446.jpg" max-height="500">
        <p class="header-title">過去の演奏</p>
      </v-img>
    </v-container>
    <v-container>
      <v-row>
        <v-col
          v-for="videoInfo in videoInfos"
          v-bind:key="videoInfo.id"
          xl="4"
          lg="6"
          md="6"
          cols="12"
        >
          <div>
            <youtube
              :video-id="videoInfo.id"
              ref="youtube"
              :width="300"
              :height="180"
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
import VueYoutube from 'vue-youtube'

Vue.use(VueYoutube)

export default {
  head() {
    return { title: '過去の演奏' }
  },
  data() {
    return {
      videoInfos: [
        {
          id: 'mAkZT5KPuiI',
          title: 'かもめ　男声合唱組曲「中勘助の詩から」より　合唱団ばすけ'
        },
        {
          id: 'uafxh1cn_t4',
          title: '北の海鳥　男声合唱組曲「海鳥の詩」より　合唱団ばすけ'
        },
        {
          id: 'kFu_x_cw9n0',
          title: 'エトピリカ　男声合唱組曲「海鳥の詩」より　合唱団ばすけ'
        },
        {
          id: 'Ligje2YhazU',
          title: '波乗りジョニー　合唱団ばすけ'
        },
        {
          id: 'LLbl0W2QOTk',
          title:
            '新しい時代に　男声合唱とピアノのための「わが詩友」より　合唱団ばすけ'
        },
        {
          id: 'wf5Oo0WvXbk',
          title:
            '川よとわに美しく　男声合唱組曲「川よとわに美しく」より　合唱団ばすけ'
        },
        {
          id: 'Xl40kp20RrM',
          title: '夏の終わり 　合唱団ばすけ'
        },
        {
          id: 'ZxNcJS6T_EA',
          title: '数珠かけ鳩　男声合唱組曲「白き花鳥図」より　合唱団ばすけ'
        },
        {
          id: 'Sqv-Yf-ehz0',
          title: '黎明　男声合唱組曲「白き花鳥図」より　合唱団ばすけ'
        }
      ]
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
  props: {
    resize: true
  }
}
</script>

<style scoped>
.container--fluid {
  padding: 0px;
}
.header-title {
  color: #fcfcfc;
  font-family: 'M PLUS Rounded 1c';
  font-weight: 700;
  font-size: xx-large;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  margin: 0;
  padding: 0;
}
</style>
