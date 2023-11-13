<script setup>
import { ref } from 'vue'
const msg = ref('Input Text')
</script>

<template>
    <h3>テキストを入力すると、ラベルは変更できる。</h3>
    <input v-model="msg">
    <h2>{{ msg }}</h2>
    <hr>
</template>

<style scoped>
h2 {
    font-size: 1.8rem;
    color: greenyellow;
}
</style>