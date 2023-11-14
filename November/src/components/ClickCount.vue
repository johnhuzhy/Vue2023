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
    <p>ボタンをクリックすると、カウントできる。</p>
    <button @click="increment">Count is: {{ count }}</button>
    <br>
    <time :title="date" :datetime="date">
        クリック時刻は <span class="font-red">{{ formatDate(date) }}</span> 。
    </time>
</template>

<style scoped>
button {
  font-weight: bold;
  color: red;
}
.font-red {
    font-style: italic;
    color: red;
}
</style>