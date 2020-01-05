<template>
  <v-layout>
    <v-flex class="text-center">
      <v-container fluid>
        <v-img
          src="IMG_1446.jpg"
          alt="ヘッダー"
          class="header-img"
          max-height="500"
        >
          <p class="header-title">HogeFugaPiyo</p>
        </v-img>

        <v-row class="mb-10" justify="center">
          <v-col xl="12" lg="12" md="12" cols="12">
            <div class="explession othercontents">
              <h1 class="subtitle">合唱団ばすけとは</h1>
              <img
                src="../components/figures/basketball.png"
                alt="バスケットボールだよ"
                class="pictures"
              />
              <p class="extext">
                合唱団ばすけは、早稲田大学合唱団のOBが集まって結成された男性合唱団です。
              </p>
            </div>
          </v-col>
        </v-row>

        <v-row class="mb-10" justify="center">
          <v-col xl="12" lg="12" md="12" cols="12">
            <h1 class="subtitle">団員紹介</h1>
          </v-col>
          <v-col xl="4" lg="4" md="4" cols="12">
            <div class="explession">
              <h2 class="position">団長</h2>
              <h2 class="names">戸倉しんちゃん</h2>
              <img
                src="../components/figures/sin.jpg"
                alt="とくらさんの画像だよ"
                class="pictures"
                id="sin"
              />
              <p class="extext">
                戸倉さんはすごいんだぞウホウホウホウホウホウホウホウホ
              </p>
            </div>
          </v-col>
          <v-col xl="4" lg="4" md="4" cols="12">
            <div class="explession">
              <h2 class="position">指揮者</h2>
              <h2 class="names">川崎えももん</h2>
              <img
                src="../components/figures/emo.jpg"
                alt="えもさんの画像だよ"
                class="pictures"
              />
              <p class="extext">
                えもさんはすごいんだぞウホウホウホウホウホウホウホウホ
              </p>
            </div>
          </v-col>
          <v-col xl="4" lg="4" md="4" cols="12">
            <div class="explession">
              <h2 class="position">ピアニスト</h2>
              <h2 class="names">吉田りえ神</h2>
              <img
                src="../components/figures/rie.jpg"
                alt="りえさんの画像だよ"
                class="pictures"
              />
              <p class="extext">りえさんはすごい</p>
            </div>
          </v-col>
        </v-row>

        <v-row class="mb-10" justify="center">
          <v-col xl="12" lg="12" md="12" cols="12">
            <div class="explession othercontents">
              <h1 class="subtitle">連絡先</h1>
              <img
                src="../components/figures/postit.jpg"
                alt="ポストイットだよ"
                class="pictures"
              />
              <p class="extext">
                これが連絡先だけど団員受け付けてないから連絡してくんなよ
              </p>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-flex>
  </v-layout>
</template>

<style scoped>
.text-center {
  color: #535353;
  font-family: Meiryo, sans-serif;
}

.header-img {
  margin: 0 0 40px 0;
}

.header-title {
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

.subtitle {
  margin: 0 0 40px 0;
  font-weight: 400;
  font-size: 40px;
}

.exploession {
  align-content: center;
}

.othercontents {
  width: 70%;
  margin: auto;
}

.position {
  font-weight: normal;
  font-size: 20px;
}

.names {
  font-weight: 400;
  font-size: 30px;
}

.pictures {
  width: 70%;
  border-radius: 5px;
  margin: 0 0 15px 0;
}

.box {
  position: relative;
}

.active {
  margin: auto;
  background-color: orange;
  position: absolute;
  top: 0;
}

.extext {
  padding: 0 15% 0 15%;
  font-size: 20px;
}

.container--fluid {
  padding: 0px;
}
</style>
