<script>
import { useStore } from "vuex";

export default {
  name: "Footer",
  setup() {
    const store = useStore();
    const btnDeleteAll = () => {
      store.dispatch("clearTodo");
    };
    return { btnDeleteAll };
  },
};
</script>

<template>
  <footer>
    <button @click="btnDeleteAll">Clear All</button>
  </footer>
</template>

<style scoped>
footer {
  width: 100%;
  height: auto;
  text-align: center;
  box-sizing: border-box;
}
footer > button {
  width: 100px;
  height: 30px;
  color: #e20303;
}
</style>
