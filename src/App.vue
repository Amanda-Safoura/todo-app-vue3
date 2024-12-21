<template>
  <div class="container mt-5" style="max-width: 750px">
    <h2 class="text-center">Todo App</h2>
    <form action="" method="post" class="my-5 align-items-center" @submit.prevent="createNewTodo">
      <div class="row g-2">
        <input
          class="form-control"
          type="text"
          name="todo"
          id="add_todo"
          placeholder="Ajouter une nouvelle tâche"
          v-model="newTodoTitle"
        />
        <button type="submit" class="btn btn-primary" :disabled="newTodoTitle == ''">Add</button>
      </div>
    </form>

    <div class="mt-0 mb-3">
      <div class="form-check form-check-inline">
        <input
          class="form-check-input"
          type="checkbox"
          id="hideDoneTasks"
          v-model="hideDoneTasks"
        />
        <label class="form-check-label" for="hideDoneTasks">Masquer les tâches terminées</label>
      </div>
    </div>

    <div v-if="todoArr.length == 0" class="fs-5 text-center">Aucune tâche actuellement</div>
    <div v-else>
      <ul v-for="todo in todoArr" :key="todo.date">
        <li>
          <div :class="{ 'form-check': true, 'd-none': hideDoneTasks && todo.completed }">
            <input
              :class="{ 'form-check-input': true, 'text-decoration-line-through': todo.completed }"
              type="checkbox"
              :checked="todo.completed"
              :id="`todo-${todo.date}`"
              @change="updateCompletedBool(todo)"
            />
            <label class="form-check-label" :for="`todo-${todo.date}`">
              {{ todo.title }}
            </label>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const newTodoTitle = ref('')
const todoArr = ref([])

const createNewTodo = () => {
  if (newTodoTitle.value != '') {
    const newTodo = {
      title: newTodoTitle.value,
      date: Date.now(),
      completed: false
    }

    todoArr.value.push(newTodo)
    sortTodoArr()
    newTodoTitle.value = ''
  }
}

const sortTodoArr = () => {
  todoArr.value.sort((a, b) => (a.completed >= b.completed ? 1 : -1))
}
const updateCompletedBool = (todo) => {
  todo.completed = !todo.completed
  sortTodoArr()
}

const hideDoneTasks = ref(false)
</script>

<style>
ul {
  list-style: none;
}
</style>
