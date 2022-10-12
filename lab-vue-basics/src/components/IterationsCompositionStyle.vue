<template>

    <h1 class="title is-1">Composition API</h1>
    <hr>
    <hr>
    <div id="iteration1">
        <h2 class="title is-2">Iteration 1:</h2>
        <p>Create a basic template structure inside a new project (NavBar + Footer)</p>
    </div>
    <hr>
    <hr>
    <div id="iteration2">
        <h2 class="title is-2">{{message}}</h2>
        <p>Display the result of a Javascript operation in a component's HTML</p>
        <h2 class="subtitle">{{ 2 + 2 }}</h2>
        <hr>
        <h2 class="subtitle">{{ message2() }}</h2>
    </div>
    <hr>
    <hr>
    <div id="iteration3">
        <h2 class="title is-2">Iteration 3</h2>
        <p>Show an element only if a particular property is set to true</p>
        <button @click="toggle">v-if toggle</button>
        <h2 v-if="awesome">You're awesome!</h2>
        <h2 v-else>🤩</h2>
        <hr>
        <button @click="toggle2">v-show toggle</button>
        <h1 v-show="awesome2">... sure?</h1>
    </div>
    <hr>
    <hr>
    <div id="iteration4">
        <h2 class="title is-2">Iteration 4</h2>
        <p>Display a list of elements that are stored inside a component</p>
        <div v-for="(post, index) in data" :key="index">
            <h1>Post title: {{ post.title }}</h1>
            <h4>Post description: {{ post.description }}</h4>
            <p>Post content: {{ post.content }}</p>
        </div>
    </div>
    <hr>
    <hr>
    <div id="iteration5">
        <h2 class="title is-2">Iteration 5</h2>
        <p>Bonus | Change the background color of an element when pressing a button</p>
        <div class="color-block" :style="{backgroundColor: bgColor}"></div>
        <button @click="getColor">Change color!</button>
    </div>

</template>




<script setup>

import { reactive, ref } from 'vue'

const message = ref('Iteration 2')
const message2 = () => `Return this message`


const awesome = ref(true)
const toggle = () => awesome.value = !awesome.value

const awesome2 = ref(false)
const toggle2 = () => awesome2.value = !awesome2.value

const data = ref([
    { title: "Hola", description: "caracola", content: "Lorem ipsum" },
    { title: "Hola2", description: "caracola2", content: "Lorem ipsum2" },
    { title: "Hola3", description: "caracola3", content: "Lorem ipsum3" },
])

const bgColor = ref("pink");

const getColor = () => {
    const r = Math.floor(Math.random() * 255);
    const g = Math.floor(Math.random() * 255);
    const b = Math.floor(Math.random() * 255);
    bgColor.value = `rgb(${r}, ${g}, ${b})`
}

</script>




<style scoped>
* {
    margin-left: 20px;
}

p {
    margin-bottom: 30px;
}

.color-block {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    margin: 20px 40px;
}
</style>