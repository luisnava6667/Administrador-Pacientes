<script setup>
import {computed } from 'vue'
const props = defineProps({
  alerta: {
    type: Object,
    required: true
  }
})
const isError = computed(() =>{
    return props.alerta.tipo === 'error'
})
</script>

<template>
  <div
    :class="[isError ? 'bg-red-500' : 'bg-green-500']"
    class="p-3 text-center text-white uppercase font-bold rounded-md mb-3"
    >
    {{ alerta.mensaje }}
  </div>
</template>
