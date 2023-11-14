<script setup>
import { ref } from 'vue'
const msg = ref('Input Text')
</script>

<template>
    <p>テキストを入力すると、ラベルは変更できる。</p>
    <input v-model="msg">
    <h2>{{ msg }}</h2>
</template>

<style scoped>
h2 {
    font-size: 1.8rem;
    color: greenyellow;
}
</style>