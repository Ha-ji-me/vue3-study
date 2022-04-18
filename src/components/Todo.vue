<script setup lang="ts">
import { ref, reactive } from 'vue'

const todoItem = ref<string>('');
// const todoItem2 = '筋トレ';
const todoHour = ref<string>('');

const url1 = 'https://www.doutor.co.jp/dcs/';
const url2 = 'https://www.anytimefitness.co.jp/';

const isComplete = () => {
    if(todoItem == ''){
        alert('todoを設定しましょう！')
    }else{
        alert('「' + todoItem + '」' + 'を本当に完了しましたか？')
    }
    
}

const memberInfo = {
    isMember: true,
    isPremier: false,
}

const inputTodo = (event:any) => {
    // console.log('event:',event.target.value)
    todoItem.value = event.target.value
}
// const inputHour = (event:any) => {
//     todoHour.value = event.target.value
// }
// ようはこれ、v-modelで一瞬で実現できることをやっちゃってる
</script>



<template>
<div class="container">
    <hr>
    <label>Todoリスト</label>
    <hr>
    <div class="memberRank">
        <p v-if="memberInfo.isMember == true">あなたは一般会員です。</p>
        <p v-else-if="memberInfo.isPremier == true">あなたはプレミアム会員です。</p>
        <p v-else>あなたは不正なユーザーです。</p>
    </div>

    <div class="flex">
        <div class="field">
            <!-- 自作で作ったらこれになった -->
            <input  type="text" v-on:input="inputTodo"/>
            <button id="addTodo">todo追加</button>
        </div>
        <div class="field">
            <!-- 調べてみたら上記と全く同じことがv-modelを使っただけで一行で実現した。 -->
            <input type="text" v-model="todoHour"/>
            <button id="addTodo">時間追加</button>
        </div>
    </div>

    <div class="addedTodo">
        <div class="field">
            <label class="todo">Todo：{{todoItem}}</label>
        </div>
        <div class="field">
            <label class="hour">Hour：{{todoHour}}</label>
        </div>
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
</div>
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
.field {
    margin:10px;
}
.memberRank {
    font-size:20px;
    font-weight:bold;
}
</style>