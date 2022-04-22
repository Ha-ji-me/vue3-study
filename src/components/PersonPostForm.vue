<script setup lang="ts">
import { ref } from 'vue'
const addForm = () => {
    alert('Do you really register column??')
}

</script>

<template>
<div class="form-container">
    <div class="input-container">
        <div class="input-column">
            <span>name:</span>
            <input>
        </div>
        <div class="input-column">
            <span>age:</span>
            <input>
        </div>
    </div>
    <button @click="addForm" class="add-button">register</button>
</div>
</template>

<style scoped>
.form-container {
    display: flex;
    flex-direction: column;
    align-items:center;
    background-color: rgb(255, 241, 226);
    padding: 24px 0px; 
    width: 50%;
    margin-bottom: 12px;
    border-radius: 4px;
}

.input-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 50px;
    margin-bottom :20px;
}

.input-column {
    width: 200px;
    display: flex;
    justify-content: space-between;
}

input {
    width: 120px;
    margin-bottom: 8px;
}

span {
    font-size: 20px;
    font-weight: bold;
}

</style>