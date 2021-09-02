<template>
  <v-app dark>
    <Header />
    <v-main>
      <v-lazy
        v-model="isActive"
        :options="{
          threshold: 1
        }"
        transition="scroll-x-transition"
      >
        <v-container>
          <Nuxt />
          <Footer />
        </v-container>
      </v-lazy>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      isActive: false
    };
  }
};
</script>
