<template>
  <Navbar />

  <Todo />

  <Uncompleted />

  <Completed />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Todo from "./components/Todo.vue";
import Uncompleted from "./components/Uncompleted.vue";
import Completed from "./components/Completed.vue";

export default {
  components: { Navbar, Todo, Uncompleted, Completed },
  data() {
    return {
      count: 0,
    };
  },
};
</script>
