<template>
  <div
    class="card-wrapper"
    @click="toggle"
  >
  <!-- Foreground -->
    <div class="foreground">
      <p class="date">{{ getDate(index) }}</p>
    </div>
  <!-- Background -->
    <div
      class="background"
      :class="{ 'hide': hide === true }"
    >
      <p class="date">{{ getDate(index) }}</p>
      <div class="content">
        <img
          class="icon"
          :src="item.icon"
        >
        <div class="text">
          <div class="temp">
            <p>Temperatur:</p>
            <ul>
              <li>
                <p>Real:</p>
                <p><span>{{item.temp.real}}</span> C°</p>
              </li>
              <li>
                <p>Gefühlt:</p>
                <p><span>{{item.temp.feel}}</span> C°</p>
              </li>
            </ul>
          </div>
          <div class="rain">
            <ul>
              <li>Regen:</li>
              <li><span>{{item.rain}}</span> %</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    item: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      date: new Date(),
      dates: ['SO', 'MO', 'DI', 'Mi', 'DO', 'FR', 'SA'],
      hide: true,
    };
  },
  mounted() {
    // DEBUG
    /* eslint-disable */
    // console.log();
     /* eslint-enable */
  },
  methods: {
    /* eslint-disable */
    getDate(index) {
      let date = this.date.getDay() + index;
      if (date > 6) date %= 7;
      return this.dates[date];
    },
    toggle() {
      this.hide = !this.hide;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card-wrapper {
  position: relative;
  width: 250px;
  height: 175px;
  display: flex;
  justify-content: center;
  overflow: hidden;
  align-items: center;
  box-shadow: 0 3px 6px rgba(0, 0, 0, .3);
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.background,
.foreground {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: white;
}

.background {
  opacity: 1;
  transition: opacity .4s;
}

.background.hide{
  opacity: 0;
  transition:
    opacity .4s
  ;
}

.foreground .date {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin: 0;
  font-size: 46px;
  font-weight: bolder;
}

.background .date {
  margin: 0;
  padding: 10px;
  text-align: left;
}

.content {
  display: flex;
  align-items: flex-start;
}

.icon {
  display: block;
  width: 33.3%;
  padding-left: 10px;
}

.text {
  width: 66.6%;
  text-align: left;
  padding: 0 10px;
}

.temp ul {
  padding-left: 10px;
}

.temp ul li {
  display: flex;
  justify-content: space-between;
  margin: 5px 0;

  p {
    margin: 0;
  }
}

.temp >  p {
  margin: 5px 0;
}

.rain ul {
  padding-left: 10px;
  display: flex;
  justify-content: space-between;
  margin: 5px 0;

  p {
    margin: 0;
  }
}
</style>
