<template>
  <div>
    <v-container fluid>
      <v-img src="IMG_1446.jpg" max-height="500">
        <p class="image-title">
          <span class="line-break">合唱団ばすけ</span>
          <span class="line-break">5周年記念演奏会</span>
        </p>
      </v-img>
    </v-container>
    <v-container>
      <h1 class="main-title">
        <span class="line-break">合唱団ばすけ</span
        ><span class="line-break">５周年記念演奏会</span>
      </h1>
      <v-row>
        <v-col xl="4" lg="4" md="4" cols="12">
          <v-card class="details mb-4">
            <v-card-text>
              <h2>開催日程</h2>
              <div>2020年2月23日</div>
              <p>
                <span class="pr-2">開場&nbsp;16:00</span
                ><span>開演&nbsp;16:30</span>
              </p>
              <h2>会場</h2>
              <p>
                <span class="mr-1 line-break">早稲田奉仕園スコットホール</span
                ><span class="line-break">(東京都新宿区西早稲田2-3-1)</span>
              </p>
              <h2>アクセス</h2>
              <p class="mb-1">
                <span class="mr-1 line-break">東京メトロ東西線</span
                ><span class="line-break">早稲田駅より徒歩5分</span>
              </p>
              <p class="mb-1">または</p>
              <p class="mb-0">
                <span class="mr-1 line-break">東京メトロ副都心線</span
                ><span class="line-break">西早稲田駅より徒歩8分</span>
              </p>
              <a href="https://www.hoshien.or.jp/"
                >https://www.hoshien.or.jp/</a
              >
              <v-card>
                <div class="google-map">
                  <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3239.7485058851025!2d139.71407491448812!3d35.70780598018814!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188d1bfff8e65d%3A0x880c3c3d129851b5!2z5pep56iy55Sw5aWJ5LuV5ZySIOOCueOCs-ODg-ODiOODm-ODvOODqw!5e0!3m2!1sja!2sjp!4v1577465807042!5m2!1sja!2sjp"
                    width="100%"
                    height="auto"
                    frameborder="0"
                    style="border:0;"
                    allowfullscreen
                  ></iframe>
                </div>
              </v-card>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col xl="8" lg="8" md="8" cols="12">
          <v-card class="details mb-4">
            <v-card-text>
              <h2>プログラム</h2>
              <div
                class="mb-1"
                v-for="stage in stages"
                :key="stage.stage_title"
              >
                <h3 class="hidden-sm-and-down">
                  {{ stage.stage_order }}&nbsp;{{ stage.stage_title }}
                </h3>
                <h3 class="hidden-md-and-up">
                  <div>{{ stage.stage_order }}</div>
                  <div>{{ stage.stage_title }}</div>
                </h3>
                <p class="mb-0" v-for="song in stage.songs" :key="song.title">
                  {{ song.title }}
                </p>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <div class="flyer"><v-img src="recital_flyer.jfif"></v-img></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stages: [
        {
          stage_order: '1st Stage',
          stage_title: '多田武彦男声合唱曲集より',
          songs: [
            { title: '鐘鳴りぬ', composer: '多田武彦', lyric: '三好達治' },
            { title: 'さくら散る', composer: '多田武彦', lyric: '草野心平' },
            { title: '柳川', composer: '多田武彦', lyric: '北原白秋' }
          ]
        },
        {
          stage_order: '2nd Stage',
          stage_title: 'アラカルトステージ',
          songs: [
            { title: '初心のうた', composer: '信長貴富', lyric: '木島始' },
            { title: 'ブルー', composer: '北川昇', lyric: 'みなづきみのり' },
            { title: 'みょうが', composer: '新実徳英', lyric: '星野富弘' },
            {
              title: 'カウボーイ・ポップ',
              composer: '信長貴富',
              lyric: '寺山修司'
            },
            { title: '輪舞', composer: '清水脩', lyric: '近藤鏡二郎' }
          ]
        },
        {
          stage_order: '3rd Stage',
          stage_title: '男声合唱曲「季節へのまなざし」',
          songs: [
            { title: 'ひらく', composer: '荻久保和明', lyric: '伊藤海彦' },
            { title: 'のびる', composer: '荻久保和明', lyric: '伊藤海彦' },
            { title: 'みのる', composer: '荻久保和明', lyric: '伊藤海彦' },
            { title: 'ゆめみる', composer: '荻久保和明', lyric: '伊藤海彦' }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.container--fluid {
  padding: 0px;
}
.image-title {
  color: #fcfcfc;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  margin: 0;
  padding: 0;
}
.main-title {
  text-align: center;
}
.details {
  text-align: center;
}
.flyer {
  margin: 0 auto;
  width: 80vw;
  height: auto;
}
.google-map {
  position: relative;
  width: 100%;
  height: 100%;
  padding-top: 75%;
  margin-top: 1em;
}
.google-map iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.line-break {
  display: inline-block;
}
ul {
  list-style: none;
  padding: 0;
}
</style>
