<script setup lang="ts">

const todoItem = '勉強';
const todoItem2 = '筋トレ';

const url1 = 'https://www.doutor.co.jp/dcs/';
const url2 = 'https://www.anytimefitness.co.jp/';

const isComplete = (todoItem : string) => {
    alert(todoItem + 'を本当に完了しましたか？')
}

</script>

<template>
    <hr>
    <label>Todoリスト</label>
    <hr>
    <div>
        <label class="todo">内容：{{todoItem}}</label>
        <!-- <a href="https://www.doutor.co.jp/dcs/">開催場所</a> -->
        <div>
            開催場所：<a v-bind:href="url1">こちら</a>
        </div>
        <button v-on:click="isComplete(todoItem)">完了</button>
    </div>
    <div>
        <label class="todo">内容：{{todoItem2}}</label>
        <div>
            開催場所：<a v-bind:href="url2">こちら</a>
        </div>
        <button v-on:click="isComplete(todoItem2)">完了</button>
    </div>

</template>

<style scoped>
label {
    font-size: 80px;
    font-weight: bold;
    color: green;
}
.todo {
    font-size:30px;
    color:black;
    margin-bottom:8px;

}
</style>