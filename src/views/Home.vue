<template>
  <div class="home">
    <img class="logo" src="../assets/logo.png">
    <h1>Vue.js Vorstellung</h1>
    <p>powered by freischwimmer</p>

    <!-- Card -->
    <lecture class="lecture">
      <div class="card-container">
        <card
          v-for="(card, index) in cards"
          :key="Math.round(Math.random() * 100) * index + index"
          :item="card"
          :index="index"
        />
      </div>
    </lecture>
    
    <lecture>
      <fs-list />
    </lecture>
  </div>
</template>

<script>
import Card from '@/components/card.vue';
import Lecture from '@/components/LectureApp.vue';
import fsList from '@/components/fsList.vue';

export default {
  name: 'home',
  components: {
    Lecture,
    Card,
    fsList,
  },
  data() {
    return {
      cards: [
        {
          icon: 'https://image.flaticon.com/icons/svg/248/248823.svg',
          temp: {
            real: 15,
            feel: 12,
          },
          rain: Math.round(Math.random() * 100),
        },
        {
          icon: 'https://image.flaticon.com/icons/svg/248/248808.svg',
          temp: {
            real: 19,
            feel: 15,
          },
          rain: Math.round(Math.random() * 100),
        },
        {
          icon: 'https://image.flaticon.com/icons/svg/248/248771.svg',
          temp: {
            real: 25,
            feel: 23,
          },
          rain: Math.round(Math.random() * 100),
        },
      ],
    };
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

.card-container {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

</style>
