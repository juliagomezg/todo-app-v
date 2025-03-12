<template>
  <div class="min-h-screen bg-gray-100 flex items-center justify-center p-4">
    <div class="bg-white shadow-lg rounded-lg p-6 w-full max-w-md">
      <h1 class="text-2xl font-bold text-center mb-4">ToDo App V</h1>

      <!-- Input + Botón -->
      <div class="flex gap-2 mb-4">
        <input
          v-model="newTask"
          @keyup.enter="addTask"
          type="text"
          placeholder="Escribe una nueva tarea"
          class="flex-1 border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
        />
        <button
          class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600"
          @click="addTask"
        >
          Agregar
        </button>
      </div>

      <!-- Lista de tareas -->
      <ul class="space-y-2">
        <li
          v-for="(task, index) in tasks"
          :key="index"
          class="border p-2 rounded flex justify-between items-center"
          :class="{ 'line-through text-gray-400': task.completed }"
          @click="toggleTask(index)"
        >
          {{ task.text }}
          <!-- Botón eliminar (desactivado por ahora) -->
          <button
            class="text-red-500 hover:text-red-700"
            disabled
          >
            ✖️
          </button>
        </li>

        <!-- Mensaje si no hay tareas -->
        <li v-if="tasks.length === 0" class="text-gray-500 text-center">
          No hay tareas aún
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// Lista de tareas con estado de completada
interface Task {
  text: string
  completed: boolean
}

const tasks = ref<Task[]>([])
const newTask = ref('')

// Función para añadir tareas
const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push({ text: newTask.value.trim(), completed: false })
    newTask.value = ''
  }
}

// Función para marcar/desmarcar tarea como completada
const toggleTask = (index: number) => {
  tasks.value[index].completed = !tasks.value[index].completed
}
</script>