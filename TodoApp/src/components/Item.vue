<template>
  <li v-for="(todo, index) in todos">
    <i class="fa fa-check" aria-hidden="true"></i>
    <span>{{ todo }}</span>
    <button @click="btnRemove(index)">삭제</button>
  </li>
</template>
<script>
import { useStore } from "vuex";
import { computed } from "vue";

export default {
  name: "Item",

  setup() {
    const store = useStore();
    const todos = computed(() => store.getters.todos);

    const btnRemove = (index) => {
      console.log(" index : " + index);
      store.dispatch("removeTodo", index);
    };
    return { todos, btnRemove };
  },
};
</script>
<style scoped></style>
