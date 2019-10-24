<template>
  <div class="fs-list">
    <ul>
      <fs-list-item v-for="elm in list"
                    :key="elm.id"
                    :id="elm.id"
                    @delete="deleteElm">
        {{ elm.content }}
      </fs-list-item>
    </ul>
    <form v-on:submit.prevent="createElm">
      <input v-model="newItem" placeholder="Neuer Eintrag" />
      <input type="submit" value="Hinzufügen">
    </form>
  </div>
</template>

<script>
import fsListItem from '@/components/fsListItem.vue';

export default {
  name: 'fs-list',
  components: {
    fsListItem,
  },
  data() {
    return {
      parentID: 1,
      newItem: '',
      list: [
        {
          id: 0,
          content: 'List Item Test',
        },
      ],
    };
  },
  methods: {
    deleteElm(currID) {
      const newList = [];
      this.list.map((elm) => {
        if (elm.id !== currID) {
          newList.push(elm);
        }
        return 0;
      });
      this.list = newList;
    },
    createElm() {
      const newElm = {
        id: this.parentID,
        content: this.newItem,
      };
      this.list.push(newElm);
      this.newItem = '';
      this.parentID += 1;
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
