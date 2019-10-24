<template>
  <div class="home">
    <img class="logo" src="../assets/logo.png">
    <h1>Vue.js Vorstellung</h1>
    <p>powered by freischwimmer</p>
    <lecture/>
  </div>
</template>

<script>
import Lecture from '@/components/LectureApp.vue';

export default {
  name: 'home',
  components: {
    Lecture,
  },
};
</script>

<style lang="scss" scoped>
// General
.home {
  padding: 45px;
}

// Vue.js Logo
.logo {
  display: block;
  position: relative;
  margin: 0 auto;
}

</style>
