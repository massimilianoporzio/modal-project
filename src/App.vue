<template>

  <h1>{{titolo}}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
</template>

<script setup>
import {ref} from "vue";
let titolo = 'ciao'
let name = ref(null)
function  handleClick(e)
{
  const el = name.value
  el.classList.add('active')
  el.focus()
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
