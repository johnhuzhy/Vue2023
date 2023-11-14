<script setup>
import { ref } from 'vue'
const header = ref('Front FrameWork List!')
const items = ref([
    {id: 1, label: "Angular"},
    {id: 2, label: "React"},
    {id: 3, label: "Vue"}
])
const newItem = ref("")
const scriptType = ref([])

const addItem = ()=>{
    if (newItem.value !== "") {
        items.value.push({id: items.value.length + 1, label: newItem.value})
    }
    newItem.value = ""
}
</script>

<template>
    <h2>{{ header }}</h2>
    <input type="text" v-model.trim="newItem" v-on:keyup.enter="addItem" placeholder="Input New Item">
    <button class="btn-margin btn-square" v-on:click="addItem">Add</button>
    <br>
    <ul>
        <li v-for="{id, label} in items" :key="id">{{ label }}</li>
    </ul>
    <label><input type="checkbox" value="typescript" v-model="scriptType">TypeScript</label>
    <label><input type="checkbox" value="javascript" v-model="scriptType">JavaScript</label>
    <p>{{ scriptType }}</p>
</template>

<style scoped>
h2 {
    font-size: 1.8rem;
    color: blueviolet;
    padding: 0;
}
</style>