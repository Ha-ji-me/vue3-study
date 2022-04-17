<script setup lang="ts">
import { ref, reactive } from 'vue'

const todoItem = ref<string>('');
// const todoItem2 = '筋トレ';
const todoHour = ref<string>('');

const url1 = 'https://www.doutor.co.jp/dcs/';
const url2 = 'https://www.anytimefitness.co.jp/';

const isComplete = (todoItem : string) => {
    alert(todoItem + 'を本当に完了しましたか？')
}

const inputTodo = (event:any) => {
    console.log('event:',event.target.value)
    todoItem.value = event.target.value
}
const inputHour = (event:any) => {
    todoHour.value = event.target.value
}
</script>



<template>
    <hr>
    <label>Todoリスト</label>
    <hr>
    <div class="flex">
        <input  type="text" v-on:input="inputTodo"/>
        <button id="addTodo">todo追加</button>
        <input type="text" v-on:input="inputHour"/>
        <button id="addTodo">時間追加</button>
    </div>

    <div class="addedTodo">
        <label class="todo">Todo：{{todoItem}}</label>
        <p></p>
        <label class="hour">Hour：{{todoHour}}</label>
        <!-- <div>
            開催場所：<a v-bind:href="url1">こちら</a>
        </div> -->
        <button v-on:click="isComplete(todoItem)">完了</button>
    </div>
    <!-- <div>
        <label class="todo">内容：{{todoItem2}}</label>
        <div>
            開催場所：<a v-bind:href="url2">こちら</a>
        </div>
        <button v-on:click="isComplete(todoItem2)">完了</button>
    </div> -->
</template>



<style scoped>
.todo {
    font-size: 80px;
    font-weight: bold;
    color: green;
    font-size:30px;
    color:black;
    margin-bottom:8px;
    padding:20px;
}
.hour {
    font-size: 80px;
    font-weight: bold;
    color: green;
    font-size:30px;
    color:black;
    margin-bottom:8px;
    padding:20px;

}
.addedTodo {
    display:flex;
}
.flex {
    display:flex;
    text-align:center;
    
}
.button {
    display:flex;
}
</style>