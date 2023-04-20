<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
import { useStore } from "vuex";
export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer,
  },
  setup() {
    const store = useStore();

    const addTodoHandler = (todo) => {
      // alert(todo);
      store.dispatch("addTodo", todo);
    };
    return { addTodoHandler };
  },
};
</script>

<template>
  <Header v-on:addTodo="addTodoHandler" />
  <Main />
  <Footer />
</template>

<style scoped></style>
