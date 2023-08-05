<template>
  <div>
    <NuxtWelcome />
  </div>
  <button @click="increment">Increment {{count}}</button>
  <button @click="decrement">Decrement</button>

</template>

<script setup>
import { ref } from 'vue'

const count = ref(0)

const increment = () => count.value++
const decrement = () => count.value--
</script>
