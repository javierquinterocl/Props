<script setup>
import TaskComponent from '@/components/TaskComponent.vue'
import { ref } from 'vue'

const tareas = ref(['Estudiar', 'Sacar 5.0', 'Descansar', 'Almorzar'])

function deleteTask(index){
    console.log('Borrar hijo',index)
    tareas.value.splice(index,1);
}
</script>

<template>
  <div class="bg-slate-50 w-96 shadow-md rounded-md mx-auto mt-12 px-4 py-3 box-content">
    <h1 class="text-2xl font-semibold">Tareas</h1>
    <div class="flex mt-2 mb-2">
      <input
        type="text"
        class="w-4/5 h-8 px-2 outline-none rounded-l border r py-1 border-green-600"
      />
      <span
        class="text-center rounded-r w-1/5 h-8 text-xl bg-green-600 text-white hover:bg-green-700 hover:cursor-pointer"
        >+</span
      >
    </div>
    <TaskComponent v-for="(task, index) in tareas" :key="index" :tarea="task" :index="index" @borrarTarea = "deleteTask" />
  </div>
</template>

<style scoped></style>
