<template>
  <div style="display: flex; align-items: center; justify-content: center">
    <img src="https://thecatapi.com/api/images/get?format=src&type=gif" class="image" v-if="isShow" @click="onClick" style="cursor: pointer" />
    <div v-else>loading...</div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const isShow = ref(true)

function onClick() {
  isShow.value = false
  setTimeout(() => {
    isShow.value = true
  }, 500)
}
</script>
