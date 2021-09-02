<template>
  <div class="header">
    <v-navigation-drawer v-model="drawer" fixed app stateless>
      <v-list>
        <v-list-item
          v-for="(item, i) in listItems"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>
        <nuxt-link to="/" class="text-decoration-none">
          C3 Official Site
        </nuxt-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <div class="language-select">
        <v-select
          v-model="language"
          :items="selectItems"
          append-outer-icon="mdi-earth"
          outlined
        ></v-select>
      </div>
    </v-app-bar>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

interface ListItems {
  icon: string;
  title: string;
  to: string;
}

@Component
export default class Header extends Vue {
  drawer: boolean = false;
  fixed: boolean = false;
  language: string = "日本語";
  listItems: ListItems[] = [
    {
      icon: "mdi-apps",
      title: "Top",
      to: "/"
    },
    {
      icon: "mdi-bio",
      title: "About",
      to: "/about"
    },
    {
      icon: "mdi-chart-bubble",
      title: "Community",
      to: "/community"
    },
    {
      icon: "mdi-newspaper-variant",
      title: "News",
      to: "/news"
    },
    {
      icon: "mdi-post",
      title: "Blog",
      to: "/blog"
    }
  ];
  selectItems: Array<string> = [
    "日本語",
    "English",
    "한국어",
    "中文",
    "Français",
    "العربية"
  ];
}
</script>

<style scoped>
.language-select {
  height: 100%;
}
a {
  color: white;
}
</style>
