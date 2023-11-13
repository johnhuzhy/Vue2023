<script setup>
import { ref } from 'vue'
const count = ref(0)
var date = ref(new Date())

function increment() {
  count.value++
  date = ref(new Date())
}

// gets date formatted
const formatDate = (date) => {
  const tzOffset = date.getTimezoneOffset() * 60 * 1000
  const tmp = new Date(date - tzOffset).toISOString().split('T')
  return tmp[0] + ' ' + tmp[1].split('.')[0]
}
</script>

<template>
    <h3>ボタンをクリックすると、カウントできる。</h3>
    <button @click="increment">Count is: {{ count }}</button>
    <br>
    <time :title="date" :datetime="date">
        Now is {{ formatDate(date) }}.
    </time>
    <hr>
</template>

<style scoped>
button {
  font-weight: bold;
  color: red;
}
</style>