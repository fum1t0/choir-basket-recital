<template>
  <div>
    <v-container fluid>
      <v-img
        src="headerpic1.png"
        alt="ヘッダー"
        class="header-img"
        max-height="500"
      >
        <p class="header-title">
          <span class="pc-title hidden-sm-and-down">合唱団ばすけとは</span>
          <span class="sp-title hidden-md-and-up">合唱団ばすけ</span>
          <br class="hidden-md-and-up" />
          <span class="sp-title hidden-md-and-up">とは</span>
        </p>
      </v-img>
    </v-container>
    <v-container class="sections">
      <v-row class="mb-10 section">
        <v-col xl="12" lg="12" md="12" cols="12">
          <p class="section-title">団長挨拶</p>
        </v-col>
        <v-col xl="12" lg="12" md="12" cols="12">
          <div class="explession othercontents">
            <p>
              合唱団ばすけは、早稲田大学合唱団のOBが集まって結成された男声合唱団です。
            </p>
            <p>
              主に東京都合唱祭や男声合唱フェスティバル、野外合唱コンサートなどでの演奏を目指して活動しています。
            </p>
          </div>
        </v-col>
      </v-row>

      <v-row class="mb-10 section" justify="center">
        <v-col xl="12" lg="12" md="12" cols="12">
          <p class="section-title">団員紹介</p>
        </v-col>
        <v-col
          xl="4"
          lg="4"
          md="4"
          cols="12"
          v-for="member in members"
          :key="member.name"
        >
          <v-card color="#FF6E40" height="100%">
            <v-img :src="member.img" />
            <v-card-title>{{ member.name }}</v-card-title>
            <v-card-subtitle>{{ member.position }}</v-card-subtitle>
            <v-card-text>{{ member.about }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row class="mb-10" justify="center">
        <v-col xl="12" lg="12" md="12" cols="12">
          <p class="section-title">連絡先</p>
          <p>
            連絡は
            <a :href="'mailto:' + mail">{{ mail }}</a>
            にお願いします。
          </p>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  head() {
    return { title: '合唱団ばすけとは' }
  },
  data() {
    return {
      mail: 'choirbasuke@gmail.com',
      members: [
        {
          name: '戸倉晋之介',
          img: 'sin.jpg',
          position: '団長',
          about:
            '独特の空気でばすけの雰囲気を作ってくれる団長。歌の安定感は超一流。滑り笑いの安定感も超一流。'
        },
        {
          name: '川崎萌子',
          img: 'emo.jpg',
          position: '指揮者',
          about:
            '普段見せるのほほんとした顔とは一変、指揮をする姿は俊敏でパワフル。歌声も指揮も食べっぷりも元気もりもり。'
        },
        {
          name: '吉田梨絵',
          img: 'rie.jpg',
          position: 'ピアニスト',
          about:
            '合唱団の天使！そのピアノの音色を聞けばあなたもりえちゃんのとりこに？'
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
.header-img {
  margin: 0 0 30px 0;
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
.header-title .sp-title:last-of-type {
  padding: 23.5px 47px;
}
.section:nth-of-type(n + 2) {
  margin-top: 10px;
}
.section-title {
  font-size: x-large;
  font-weight: 600;
  text-align: center;
}
.sections {
  width: 80%;
  margin: auto;
}
</style>
