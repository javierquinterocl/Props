<script setup>
const props = defineProps({
    tarea: {
        type: String,
        default: 'Tarea indefinida',
    },
    index:{
        type: Number
    }
})
const emit = defineEmits(['borrarTarea'])

function borrarTarea(index){
    emit('borrarTarea',index)
}
</script>

<template>
  <div class="flex justify-between bg-gray-200 rounded px-4 py-1 mt-2">
    {{ props.tarea }}
    <span
      class="text-center rounded-r px-2 bg-red-600 text-white hover:bg-red-700 hover:cursor-pointer" @click="borrarTarea(props.index)"
      >X</span
    >
  </div>
</template>
