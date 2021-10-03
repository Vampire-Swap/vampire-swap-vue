<template>
  <v-app>
    <vampire-navbar />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import VampireNavbar from './components/VampireNavbar/VampireNavbar.vue';

export default Vue.extend({
  name: "App",

  components: {
    VampireNavbar
  }
});
</script>

<style lang="scss">
  
</style>
