<template>
  <v-container fluid class="pa-0">
    <v-sheet
      height="100vh"
      class="d-flex align-center justify-center pa-12"
    >
      <v-row align="center" justify="center" class="text-center">
        <v-col cols="12" md="8">
          <v-img
            src="/logo.png"
            max-width="200"
            class="mx-auto mb-6 mt-n6"
          />
          <h1 class="text-h2 font-weight-bold mb-2 lxgw-wenkai-mono-tc-bold">K12EDU</h1>
          <p class="text-h3 font-weight-bold lxgw-wenkai-mono-tc-regular">讓學習變得有趣、有效率！</p>
          
          <v-btn
            color="primary"
            href="https://discord.gg/dFf4cG33dT"
            target="_blank"
            class="mx-2 font-weight-bold my-4 lxgw-wenkai-mono-tc-light"
            size="x-large"
            rounded="xl"
          >
            Discord 社群
          </v-btn>
          <v-btn
            color="deep-purple"
            href="https://game.k12edu.com"
            target="_blank"
            class="mx-2 font-weight-bold my-4 lxgw-wenkai-mono-tc-light"
            size="x-large"
            rounded="xl"
          >
            免費開始遊戲
          </v-btn>
        </v-col>
      </v-row>
    </v-sheet>

<v-sheet height="100vh">
  <v-row align="center" justify="center">
    <v-col cols="12" md="10">
      <h2 class="text-h3 font-weight-bold mb-6 text-center lxgw-wenkai-mono-tc-bold">
        產品展示
      </h2>
      <div class="service-carousel mx-auto">
        <v-carousel
          hide-delimiter-background
          cycle
          continuous
          show-arrows-on-hover
        >
          <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
          >
            <v-img
              :src="slide.src"
              gradient="to bottom, rgba(0,0,0,.4), rgba(0,0,0,.7)"
            >
              <template v-slot:default>
                <v-container
                  class="fill-height d-flex flex-column align-center justify-center text-center"
                >
                  <h3 class="white--text font-weight-bold text-h4 lxgw-wenkai-mono-tc-regular">
                    {{ slide.title }}
                  </h3>
                  <v-btn 
                    class="mt-4 font-weight-bold my-4 lxgw-wenkai-mono-tc-light"
                    size="large"
                    color="primary"
                    href="slide.url"
                    target="_blank"
                    rounded="xl"
                  >
                    前往
                  </v-btn>
                </v-container>
              </template>
            </v-img>
          </v-carousel-item>
        </v-carousel>
      </div>
    </v-col>
  </v-row>
</v-sheet>

    
    <v-sheet height="100vh">
      <v-row align="center" justify="center" class="text-center">
        <v-col cols="12" md="10">
          <h2 class="text-h3 font-weight-bold mb-6 text-center lxgw-wenkai-mono-tc-bold">介紹影片</h2>
          <div class="video-wrapper">
            <iframe
              src="https://www.youtube.com/embed/UvskgqT_YyU?si=sfYSsK89DcbM8jP9"
              title="K12EDU 介紹影片"
              frameborder="0"
              allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>
        </v-col>
      </v-row>
    </v-sheet>
  </v-container>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// 路徑從 public 資料夾根目錄開始
const slides = ref([
  { src: '/service1.png', title: '數位學習教育遊戲', url: 'https://game.k12edu.uk' },
  { src: '/service2.png', title: 'AI 學習助理', url: 'https://ai.k12edu.uk' },
  { src: '/service3.png', title: '教師管理網站', url: 'https://teacher.k12edu.uk' },
  { src: '/service4.png', title: '線上程式解題網站', url: 'https://judge.k12edu.uk' },
])
</script>


<style scoped>
/* 限制寬度為視窗 60%，並保持 16:9 比例 */
.service-carousel {
  max-width: 60vw;
  aspect-ratio: 16 / 9;
  overflow: hidden;
}
/* 讓 carousel 滿版顯示父容器 */
.service-carousel .v-carousel {
  height: 100% !important;
}
.video-wrapper {
  position: relative;
  /* 16:9 高寬比：9 / 16 = 56.25% */
  padding-bottom: 56.25%;  /* 定義容器高度 */
  height: 0;               /* 高度由 padding-bottom 決定 */
  overflow: hidden;
}
.video-wrapper iframe {
  position: absolute;
  /* 左右邊界都設 0，元素寬度小於容器時可居中 */
  left: 0; right: 0;
  margin: 0 auto;
  width: 80%;                       
  height: 80%;
}
</style>