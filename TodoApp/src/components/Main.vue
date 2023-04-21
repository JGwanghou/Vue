<script>
import Item from "./Item.vue";
import { useStore } from "vuex";
import axios from "axios";
export default {
  name: "Main",
  components: {
    Item,
  },
  setup() {
    const store = useStore();
    const todos = store.getters.todos;

    return { store, todos };
  },
};
</script>

<template>
  <main>
    <ul>
      <item />
    </ul>
  </main>
</template>

<style>
main {
  width: 100%;
  height: auto;
  padding: 10px;
  box-sizing: border-box;
}
main > ul {
  width: 100%;
  height: auto;
  list-style: none;
  padding: 0;
  box-sizing: border-box;
}
main > ul > li {
  width: 100%;
  height: 40px;
  line-height: 40px;
  padding-left: 10px;
  margin-bottom: 6px;
  background-color: white;
  box-sizing: border-box;
}
main > ul > li > i {
  color: #62acde;
}
main > ul > li > span {
  margin-left: 10px;
}
main > ul > li > button {
  width: 40px;
  height: 40px;
  float: right;
  border: none;
  color: #de4343;
}
</style>
