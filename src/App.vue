<template>
  <Navbar />

  <div class="container">
    <div class="row d-flex justify-content-center">
      <div class="col-sm-11 col-lg-8">
        <div class="row p-3 shadow my-3 d-flex justify-content-center">
          <div class="col-sm-11 col-lg-11">
            <div class="input-group my-3">
              <input
                v-model="todo"
                type="text"
                class="form-control"
                placeholder="Input Your Todo..."
                @keyup.enter="add"
              />
              <button class="btn btn-success" type="button" @click="add">
                <i class="bi bi-plus-circle"></i> ADD
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <Uncompleted :todos="todos" @del="del" @done="done" />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Uncompleted from "./components/Uncompleted.vue";

export default {
  components: { Navbar, Uncompleted },
  data() {
    return {
      todo: "",
      todos: [],
    };
  },

  methods: {
    add() {
      this.todos.unshift({ acticity: this.todo, isDone: false });
      this.todo = "";

      this.saveData();
    },
    del(indexTodo) {
      this.todos = this.todos.filter((item, index) => {
        if (index !== indexTodo) {
          return item;
        }
      });
      this.saveData();
    },
    done(indexTodo) {
      this.todos = this.todos.filter((item, index) => {
        if (index == indexTodo) {
          item.isDone = !item.isDone;
        }
        return item;
      });
      this.saveData();
    },
    saveData() {
      localStorage.setItem("D2YTODO", JSON.stringify(this.todos));
    },
  },

  created() {
    this.todos = JSON.parse(localStorage.getItem("D2YTODO"));
  },
};
</script>
