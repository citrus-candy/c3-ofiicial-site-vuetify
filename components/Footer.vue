<template>
  <v-footer padless>
    <v-card flat tile width="100%" class="text-center" color="#121212">
      <v-card-text>
        <v-btn
          v-for="(button, i) in buttons"
          :key="i"
          class="mx-4"
          :href="button.link"
          target="_blank"
          icon
        >
          <v-icon size="24px">
            {{ button.icon }}
          </v-icon>
        </v-btn>
      </v-card-text>
      <v-divider></v-divider>
      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} —
        <strong>Computer Composite Club</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

interface FooterButtons {
  icon: string;
  link: string;
}

@Component
export default class Footer extends Vue {
  buttons: FooterButtons[] = [
    {
      icon: "mdi-toy-brick",
      link: ""
    },
    {
      icon: "mdi-twitter",
      link: "https://twitter.com/c3_kyutech"
    },
    {
      icon: "mdi-youtube",
      link: "https://www.youtube.com/channel/UCeRY2jujVBYRqmilrCZytFw"
    },
    {
      icon: "mdi-github",
      link: "https://github.com/Kyutech-C3"
    },
    {
      icon: "mdi-form-select",
      link: ""
    }
  ];
}
</script>

<style scoped>
.v-footer {
  margin-top: 30px;
}
</style>
