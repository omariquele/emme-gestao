<script setup>
import { useMouse } from '@vueuse/core'
import axios from 'axios'

const { x, y } = useMouse()

onMounted(async()=>{
    const response = await axios.get('http://127.0.0.1:8000/api/test')
    console.log(response.data)
})

</script>

<template>
    <h1>Home page</h1>
    <div>pos: {{ x }}, {{ y }}</div>
    <div>
  </div>
</template>