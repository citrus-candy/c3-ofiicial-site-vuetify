<template>
  <v-row justify="center" align="center" class="flex-column">
    <v-col>
      <v-parallax
        height="600"
        src="https://www.iizuka.kyutech.ac.jp/kit/wp-content/uploads/2019/07/twitter.jpg"
      ></v-parallax>
    </v-col>
    <v-col>
      <div class="text-h3">About C3</div>
    </v-col>
    <v-col>
      <v-divider></v-divider>
    </v-col>
    <v-col>
      ここに説明を入力
    </v-col>
    <v-col>
      <div class="text-h3">About Community</div>
    </v-col>
    <v-col>
      <v-divider></v-divider>
    </v-col>
    <v-col>
      <v-carousel cycle hide-delimiter-background show-arrows-on-hover>
        <v-carousel-item v-for="(item, i) in carouselItems" :key="i">
          <v-sheet :color="item.color" height="100%" tile>
            <v-row class="fill-height" align="center" justify="center">
              <div>
                <div class="text-h2 text-center title">{{ item.title }}</div>
                <div class="text-h4 text-center">{{ item.description }}</div>
              </div>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </v-col>
    <v-col>
      <div class="text-h3">Topic News</div>
    </v-col>
    <v-col>
      <v-divider></v-divider>
    </v-col>
    <v-col>
      <TopicNewsCards />
    </v-col>
    <v-col>
      <div class="text-h3">Topic Blog</div>
    </v-col>
    <v-col>
      <v-divider></v-divider>
    </v-col>
    <v-col>
      <TopicBlogCards />
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

interface Carousel {
  title: string;
  color: string;
  description: string;
}

@Component
export default class Footer extends Vue {
  carouselItems: Carousel[] = [
    { title: "Game", color: "red", description: "ここに説明を入力" },
    { title: "CG", color: "yellow darken-2", description: "ここに説明を入力" },
    { title: "Hack", color: "blue", description: "ここに説明を入力" },
    { title: "Media Art", color: "purple", description: "ここに説明を入力" }
  ];
}
</script>

<style scoped>
.title {
  padding-bottom: 100px;
}
</style>
