<script setup>
import { ref } from 'vue'
const msg = ref('')
const strikeType = ref(false)
const fontColor = ref(false)
</script>

<template>
    <p>テキスト入力とスタイル変更</p>
    <input class="txt" v-model="msg">
    <br>
    <div class="checkbox-wrapper">
        <label><input type="checkbox" class="ikxBAC" v-model="strikeType">取消線</label>
        <br>
        <label><input type="checkbox" class="ikxBAC" v-model="fontColor">赤字</label>
    </div>
    <h2 :class="{strikethrough: strikeType, fontred: fontColor}">{{ msg }}</h2>
</template>

<style scoped>
.txt {
    width: 100%; 
    padding: 10px 15px; 
    border-radius: 3px;
    border: 2px solid #ddd; 
    box-sizing: border-box; 
}

h2 {
    font-size: 1.8rem;
    color: greenyellow;
}

label {
    text-align: center;
    margin: 10px;
}

.strikethrough {
    text-decoration: line-through;
}
.fontred {
    color: red;
}

.checkbox-wrapper .ikxBAC {
    appearance: none;
    background-color: #dfe1e4;
    border-radius: 72px;
    border-style: none;
    flex-shrink: 0;
    height: 20px;
    margin: 0;
    position: relative;
    width: 30px;
}

.checkbox-wrapper .ikxBAC::before {
    bottom: -6px;
    content: "";
    left: -6px;
    position: absolute;
    right: -6px;
    top: -6px;
}

.checkbox-wrapper .ikxBAC,
.checkbox-wrapper .ikxBAC::after {
    transition: all 100ms ease-out;
}

.checkbox-wrapper .ikxBAC::after {
    background-color: #fff;
    border-radius: 50%;
    content: "";
    height: 14px;
    left: 3px;
    position: absolute;
    top: 3px;
    width: 14px;
}

.checkbox-wrapper input[type=checkbox] {
    cursor: default;
}

.checkbox-wrapper .ikxBAC:hover {
    background-color: #c9cbcd;
    transition-duration: 0s;
}

.checkbox-wrapper .ikxBAC:checked {
    background-color: #6e79d6;
}

.checkbox-wrapper .ikxBAC:checked::after {
    background-color: #fff;
    left: 13px;
}

.checkbox-wrapper :focus:not(.focus-visible) {
    outline: 0;
}

.checkbox-wrapper .ikxBAC:checked:hover {
    background-color: #535db3;
}
</style>