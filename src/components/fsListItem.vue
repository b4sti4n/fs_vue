<template>
  <li>
    <slot />
    <button @click="$emit('delete', id)">Delete</button>
  </li>
</template>

<script>
export default {
  name: 'fs-list-item',
  props: {
    id: Number,
  },
};
</script>

<style lang="scss" scoped>
li {
  display: flex;
  justify-content: space-between;
  list-style: none;
  background-color: #dcdcdc;
  padding: 10px 20px;
  margin-bottom: 10px;
}
</style>
