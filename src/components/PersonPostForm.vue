<script setup lang="ts">
const addForm = () => {
    alert('追加しますか？')
}
const addName = () => {
    
}
const addAge = () => {
    
}
</script>

<template>
<div class="form-container">
    <p>PersonPostFormです</p>
    <div class="name-column">
        name：<input :bind="addName">
    </div>
    <div class="age-column">
        age：<input :bind="addAge">
    </div>
    <div class="add-button">
        <button @click="addForm">追加</button>
    </div>
</div>
</template>

<style scoped>
.form-container {
    margin: 50px;
    padding: 70px;
    text-align: center; 
    border: solid rgba(122, 86, 50, .6);
    border-radius: 10px;
}
.name-column {
    padding:2px;
}
.age-column {
    padding:2px;
}
.add-button {
    padding:5px;
}

</style>