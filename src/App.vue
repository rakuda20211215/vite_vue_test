<script setup>
import { computed, ref } from 'vue'

let id = 0
const todos = ref([
  { id: id, text: 'makanai', done: false },
  { id: id++, text: 'jumpei', done: false },
  { id: id++, text: 'mark', done: true },
])

const HideIsfalse = ref(true)
const filteredTodo = computed(() => (HideIsfalse.value ? todos.value : todos.value.filter((t) => !t.done)))

const todoText = ref('')
function addTodo() {
  todos.value.push({ id: id++, text: todoText.value, done: false })
  todoText.value = ''
}

function removeTodo(e) {
  todos.value = todos.value.filter((t) => t !== e)
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="todoText" />
    <button>Add todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodo" :key="todo.id">
      <input type="checkbox" v-model="todo.done" />
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="HideIsfalse = !HideIsfalse">{{ HideIsfalse ? 'visible中' : 'hide中' }}</button>
</template>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>
