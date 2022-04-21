<script setup lang="ts">
import PersonPostForm from './PersonPostForm.vue';
import PersonList from './PersonList.vue';
</script>

<template>
<p>Persons.vueです</p>
<div class="container">
    <div class="form-container">
        <PersonPostForm />
    </div>
    <div class="list-container">
        <ul>
            <PersonList />
        </ul>
    </div>
</div>

</template>

<style>
</style>