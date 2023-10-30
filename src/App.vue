<template>
  <div style="display: flex; align-items: center; justify-content: center">
    <img :src="src" class="image" @click="onClick" style="cursor: pointer" @load="onload" v-show="!loading" />
    <div v-show="loading">loading...</div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const loading = ref(true)
const src = ref('https://thecatapi.com/api/images/get?format=src&type=gif')

function onClick() {
  loading.value = true
  src.value = 'https://thecatapi.com/api/images/get?format=src&type=gif' + '&time=' + Date.now()
}

function onload() {
  loading.value = false
}
</script>
