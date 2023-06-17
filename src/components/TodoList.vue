<template>
  <ul v-if="todos.length" class="todo-list">
    <TodoListItem
      v-for="(todo, i) in todos"
      :key="todo.id"
      :label="todo.label"
      :checked="todo.checked"
      @update:checked="onUpdateChecked(i, $event)"
      @delete="onDelete(i)"
    />
  </ul>
  <div v-else class="no-todos">Looks like you're absolutely free today!</div>
</template>

<script>
import TodoListItem from "@/components/TodoListItem.vue";
import {toRaw} from "vue";

export default {
  name: 'TodoList',
  components: {TodoListItem},
  emits: ['update:todos'],
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    onUpdateChecked(index, value) {
      //
    },
    onDelete(index) {
      //
    }
  }
}
</script>

<style scoped>
ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    max-height: 200px;
    overflow: auto;
    padding: 0.5em;
}

.no-todos {
    text-align: center;
    font-size: 16px;
    padding-block: 0.5em;
    margin-block: 0.5em;
    border-block: 1px solid #b6b6b6;
}
</style>
