<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'

const bombs = ref("")

onMounted(() => {
  axios.get('/api/menu')
    .then(res => {
      bombs.value = res.data
    })
    .catch(err => {
      console.error(err)
    })
})
</script>

<template>
  <div>
    <h1>Bomb 데이터</h1>
    <ul>
      <li>
        {{ bomb }}
      </li>
    </ul>
  </div>
</template>
