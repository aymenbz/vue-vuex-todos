<template>
  <div>
    <div class="todos">
      <div class="todo" v-for="todo in getTodos" :key="todo.key">
        <div>{{ todo.title }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  import { mapGetters, mapActions } from "vuex";
  export default {
    name: "Todos",
    methods: {
      ...mapActions(["fetchTodos"])
    },
    computed: mapGetters(["getTodos"]),

    created() {
      this.fetchTodos();
    }
  };
</script>

<style scoped>
.todos {
  display: flex;
  flex-wrap: wrap;
}

.todos .todo {
  flex: 0 0 25%;
}
</style>
