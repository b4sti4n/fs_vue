<template>
  <div class="lecture-wrapper">
    <!-- Insert Content here -->
    <h3>Eine Komponente (Parent)</h3>
  </div>
</template>

<script>
export default {
  name: 'LectureApp',
  props: {
  },
  data() {
    return {

    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.lecture-wrapper {
  width: 100%;
  max-width: 1024px;
  margin: 0 auto;
  margin-top: 50px;
  padding: 20px;
  box-shadow: 0 3px 6px rgba(0, 0, 0, .3);
}

</style>
