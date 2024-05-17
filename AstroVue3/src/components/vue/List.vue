<script setup>
import { ref } from 'vue'

const data = [{tittle:'Tema 1', context:'Texto del tema 1'}, 
  {tittle:'Tema 2', context:'Texto del tema 2'},
  {tittle:'Tema 3', context:'Texto del tema 3'},
  {tittle:'Tema 4', context:'Texto del tema 4'}]
const selectedIndex = ref(0)

function showInfo(i) {
  if (i == selectedIndex.value) {
    selectedIndex.value = -1
  } else {
    selectedIndex.value = i
  }
}
</script>

<template>
  <div class="bg-blue-500 max-w-[500px] p-3 mx-auto mt-12">
    <div v-for="(theme, i) in data" :key="i" class="mb-2">
      <p 
        @click="showInfo(i)"
        class="bg-blue-300 text-blue-900 px-2 py-1 font-semibold flex justify-between items-center mb-1 hover:cursor-pointer select-none rounded"
        :class="{'bg-blue-900 text-white': selectedIndex == i}">
        {{ theme.tittle }}
        <span class="text-xl">{{ selectedIndex == i ? '-' : '+' }}</span>
      </p>
      <div v-show="selectedIndex == i"
        class="px-2 py-1 bg-blue-100 text-sm rounded h-[100px]">{{ theme.context }}</div>
      </div>
  </div>
</template>