<template>
  <div class="container">
    <div class="row d-flex justify-content-center">
      <div class="col-lg-8 col-sm-11">
        <div class="row p-3 shadow my-3 d-flex justify-content-center">
          <div class="col-sm-11 col-lg-11 py-3">
            <h4>Todo List</h4>

            <hr />
            <ul class="list-group">
              <li
                v-for="(todo, index) in todos"
                :key="todo"
                class="
                  list-group-item
                  d-flex
                  justify-content-between
                  align-items-center
                "
              >
                <span v-if="todo.isDone">
                  <i class="bi bi-check-square-fill text-success me-3"></i>
                  <del>{{
                    todo.acticity ? todo.acticity : "Data Not Found!"
                  }}</del>
                </span>
                <span v-else>{{
                  todo.acticity ? todo.acticity : "Data Not Found!"
                }}</span>

                <div class="d-flex">
                  <div v-if="todo.isDone">
                    <button
                      @click="done(index)"
                      class="btn btn-sm btn-warning rounded-pill shadow"
                    >
                      <i class="bi bi-arrow-repeat"></i>
                    </button>
                  </div>

                  <div v-else>
                    <button
                      @click="done(index)"
                      class="btn btn-sm btn-primary rounded-pill shadow"
                    >
                      <i class="bi bi-check-lg"></i>
                    </button>
                  </div>

                  <div class="mx-1"></div>
                  <button
                    @click="del(index)"
                    class="btn btn-sm btn-danger rounded-pill shadow"
                  >
                    <i class="bi bi-trash"></i>
                  </button>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: {
    todos: {
      type: Array,
      default: [],
    },
  },
  methods: {
    del(index) {
      this.$emit("del", index);
    },
    done(index) {
      this.$emit("done", index);
    },
  },
};
</script>