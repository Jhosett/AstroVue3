<script setup>

import { ref } from 'vue'

const showThemeone = ref(false)
const showThemetwo = ref(false)
const showThemethree = ref(false)
const showThemefour = ref(false)

function showInfo(index) {
  if (index == 1) {
    showThemeone.value = !showThemeone.value
    showThemetwo.value = false
    showThemethree.value = false
    showThemefour.value = false
  }

  if (index == 2) {
    showThemeone.value = false
    showThemetwo.value = !showThemetwo.value
    showThemethree.value = false
    showThemefour.value = false
  }

  if (index == 3) {
    showThemeone.value = false
    showThemetwo.value = false
    showThemethree.value = !showThemethree.value
    showThemefour.value = false
  }

  if (index == 4) {
    showThemeone.value = false
    showThemetwo.value = false
    showThemethree.value = false
    showThemefour.value = !showThemefour.value
  }
}

</script>

<template>
  
  <div class="bg-blue-500 max-w-[500px] p-3 mx-auto mt-12">
    <div class="mb-2">
      <p 
        @click="showInfo(1)"
        class="bg-blue-300 text-blue-900 px-2 font-semibold flex justify-between items-center mb-1 hover:cursor-pointer select-none rounded">
        Tema 1
        <span class="text-xl">{{ showThemeone ? '-' : '+' }}</span>
      </p>
      <div 
        v-show="showThemeone"
        class="px-2 py-1 bg-blue-100 text-sm rounded">Texto del tema 1</div>
    </div>
    <div class="mb-2">
      <p 
        @click="showInfo(2)"
        class="bg-blue-300 text-blue-900 px-2 font-semibold flex justify-between items-center mb-1 hover:cursor-pointer select-none rounded">
        Tema 2
        <span class="text-xl">{{ showThemetwo ? '-' : '+' }}</span>
      </p>
      <div 
        v-show="showThemetwo"
        class="px-2 py-1 bg-blue-100 text-sm rounded">Texto del tema 2</div>
    </div>
    <div class="mb-2">
      <p 
        @click="showInfo(3)"
        class="bg-blue-300 text-blue-900 px-2 font-semibold flex justify-between items-center mb-1 hover:cursor-pointer select-none rounded">
        Tema 3
        <span class="text-xl">{{ showThemethree ? '-' : '+' }}</span>
      </p>
      <div 
        v-show="showThemethree"
        class="px-2 py-1 bg-blue-100 text-sm rounded">Texto del tema 3</div>
    </div>
    <div class="mb-2">
      <p 
        @click="showInfo(4)"
        class="bg-blue-300 text-blue-900 px-2 font-semibold flex justify-between items-center mb-1 hover:cursor-pointer select-none rounded">
        Tema 4
        <span class="text-xl">{{ showThemefour ? '-' : '+' }}</span>
      </p>
      <div 
        v-show="showThemefour"
        class="px-2 py-1 bg-blue-100 text-sm rounded">Texto del tema 4</div>
    </div>
  </div>

</template>