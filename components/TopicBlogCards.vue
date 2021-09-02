<template>
  <v-row>
    <v-col v-for="item in cardItems" :key="item.title">
      <v-card class="mx-auto" width="300" :to="'/blog/' + item.id" nuxt>
        <v-img class="white--text align-end" height="200px" :src="item.image">
          <v-card-title>{{ item.title }}</v-card-title>
        </v-img>
        <v-card-subtitle class="pb-0">
          {{ item.date }}
        </v-card-subtitle>
        <v-card-text>
          <div class="text-left">
            <v-chip
              class="ma-1"
              v-for="(tag, i) in item.tags"
              :key="i"
              :color="tag.color"
              label
            >
              <v-icon left>
                mdi-label
              </v-icon>
              {{ tag.name }}
            </v-chip>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

interface CardItems {
  id: number;
  title: string;
  image: string;
  date: string;
  tags: { name: string; color: string }[];
}
@Component
export default class TopicNewsCards extends Vue {
  dummyImg: string =
    "https://www.wp-benricho.com/www/wp-content/uploads/2016/06/fakeimg-2.png";
  cardItems: CardItems[] = [
    {
      id: 1,
      title: "ブログ 1",
      image: this.dummyImg,
      date: "YYYY年MM月DD日",
      tags: [
        { name: "Game", color: "red" },
        { name: "Unity", color: "red" }
      ]
    },
    {
      id: 2,
      title: "ブログ 2",
      image: this.dummyImg,
      date: "YYYY年MM月DD日",
      tags: [
        { name: "Hack", color: "blue" },
        { name: "Nuxt", color: "blue" }
      ]
    },
    {
      id: 3,
      title: "ブログ 3",
      image: this.dummyImg,
      date: "YYYY年MM月DD日",
      tags: [
        { name: "CG", color: "yellow darken-2" },
        { name: "blender", color: "yellow darken-2" }
      ]
    }
  ];
}
</script>

<style scoped></style>
