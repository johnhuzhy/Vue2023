<script setup>
import { ref } from 'vue'
const header = ref('フロントのリストです：')
const items = ref([
    {id: 1, label: "Angular"},
    {id: 2, label: "React"},
    {id: 3, label: "Vue"}
])
const editing = ref(false)
const newItem = ref("")

const addItem = ()=>{
    if (newItem.value !== "") {
        items.value.push({id: items.value.length + 1, label: newItem.value})
    }
    newItem.value = ""
}
const doEdit = (e)=> {
    editing.value = e
    newItem.value = ""
}
</script>

<template>
    <header>
        <h2>{{ header }}</h2>
        <button v-if="editing" class="btn-margin  btn-flat-border" @click="doEdit(false)">
            キャンセル
        </button>
        <button v-else class="btn-margin  btn-flat-border" @click="doEdit(true)">
            追加
        </button>
    </header>
    <form v-if="editing" @submit.prevent="addItem">
        <input type="text" v-model.trim="newItem" v-on:keyup.enter="addItem" placeholder="Input New Item">
        <button v-bind:disabled="newItem.length === 0" class="btn-margin btn-square">Add</button>
    </form>
    <ul>
        <li v-for="{id, label} in items" :key="id">{{ label }}</li>
    </ul>
</template>

<style scoped>
h2 {
    font-size: 1.8rem;
    color: blueviolet;
    padding: 0;
}
</style>