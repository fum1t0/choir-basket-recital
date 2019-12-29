<template>
  <div>
    <v-container fluid>
      <v-img src="IMG_1446.jpg" max-height="500">
        <p class="image-title display-3">
          合唱団ばすけ
          <br />5周年記念演奏会
        </p>
      </v-img>
    </v-container>
    <v-container>
      <h1 class="main-title">
        <span class="mr-4">合唱団ばすけ</span><span>5周年記念演奏会</span>
      </h1>
      <v-row>
        <v-col lg="6" md="6" cols="12">
          <v-card class="details">
            <v-card-text>
              <h2>開催日程</h2>
              <p>2020年2月23日</p>
              <p>
                <span class="pr-2">開場&nbsp;16:00</span
                ><span>開演&nbsp;16:30</span>
              </p>
              <h2>会場</h2>
              <p>
                <span class="pr-2">早稲田奉仕園スコットホール</span
                ><span>(東京都新宿区西早稲田2-3-1)</span>
              </p>
              <h2>プログラム</h2>
              <div v-for="stage in stages" :key="stage.title">
                <h3>{{ stage.stage_title }}</h3>
                <ul>
                  <li v-for="song in stage.songs" :key="song">{{ song }}</li>
                </ul>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col lg="6" md="6" cols="12">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3239.7485058851025!2d139.71407491448812!3d35.70780598018814!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188d1bfff8e65d%3A0x880c3c3d129851b5!2z5pep56iy55Sw5aWJ5LuV5ZySIOOCueOCs-ODg-ODiOODm-ODvOODqw!5e0!3m2!1sja!2sjp!4v1577465807042!5m2!1sja!2sjp"
            width="600"
            height="450"
            frameborder="0"
            style="border:0;"
            allowfullscreen
          ></iframe>
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
          stage_title: '1st Stage 多田武彦男声合唱曲集より',
          songs: ['鐘鳴りぬ', 'さくら散る', '柳川']
        },
        {
          stage_title: '2nd Stage アラカルトステージ',
          songs: [
            '初心のうた',
            'ブルー',
            'みょうが',
            'カウボーイポップ',
            '輪舞'
          ]
        },
        {
          stage_title: '3rd Stage 男声合唱曲「季節へのまなざし」',
          songs: ['ひらく', 'のびる', 'みのる', 'ゆめみる']
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
  width: 50vw;
  height: auto;
}
ul {
  list-style: none;
}
</style>
