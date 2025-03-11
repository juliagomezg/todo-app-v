<template>
  <div class="min-h-screen bg-gray-100 flex items-center justify-center p-4">
    <div class="bg-white shadow-lg rounded-lg p-6 w-full max-w-md">
      <h1 class="text-2xl font-bold text-center mb-4">ToDo App V</h1>

      <!-- Input + Botón -->
      <div class="flex gap-2 mb-4">
        <input
          type="text"
          placeholder="Escribe una nueva tarea"
          class="flex-1 border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
        />
        <button
          class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600"
        >
          Agregar
        </button>
      </div>

      <!-- Lista de tareas (vacía por ahora) -->
      <ul class="space-y-2">
        <!-- Ejemplo de ítem (luego dinámico) -->
        <!-- <li class="border p-2 rounded">Ejemplo de tarea</li> -->
        <li class="text-gray-500 text-center">No hay tareas aún</li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
// Aún sin lógica, solo UI
</script>
