<template>
  <div>
    <v-container fluid>
      <v-img src="headerpic3.png" max-height="500">
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
          <v-card color="#D45A35">
            <v-card-title>{{ videoInfo.title }}</v-card-title>
            <v-card-subtitle>{{ videoInfo.subtitle }}</v-card-subtitle>
            <v-card-text>
              <div>
                <youtube
                  :video-id="videoInfo.id"
                  ref="youtube"
                  :width="300"
                  :height="130"
                  fitParent
                ></youtube>
              </div>
            </v-card-text>
          </v-card>
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
          title: 'かもめ',
          subtitle: '作詩：中勘助　作曲：多田武彦'
        },
        {
          id: 'uafxh1cn_t4',
          title: '北の海鳥',
          subtitle: '作詩：更科源蔵　作曲：廣瀬量平'
        },
        {
          id: 'kFu_x_cw9n0',
          title: 'エトピリカ',
          subtitle: '作詩：更科源蔵　作曲：廣瀬量平'
        },
        {
          id: 'Ligje2YhazU',
          title: '波乗りジョニー',
          subtitle: '作詩：桑田佳祐　編曲：野呂洸碩'
        },
        {
          id: 'LLbl0W2QOTk',
          title: '新しい時代に',
          subtitle: '作詩：丸山薫　作曲：信長貴富'
        },
        {
          id: 'wf5Oo0WvXbk',
          title: '川よとわに美しく',
          subtitle: '作詩：米田栄作　作曲：三枝成彰'
        },
        {
          id: 'Xl40kp20RrM',
          title: '夏の終わり',
          subtitle: '作詩：森山直太朗 / 御徒町凪　編曲：田中達也'
        },
        {
          id: 'ZxNcJS6T_EA',
          title: '数珠かけ鳩',
          subtitle: '作詩：北原白秋　作曲：多田武彦'
        },
        {
          id: 'Sqv-Yf-ehz0',
          title: '黎明',
          subtitle: '作詩：北原白秋　作曲：多田武彦'
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
  font-size: x-large;
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
