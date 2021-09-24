<template>

  <h1>{{titolo}}</h1>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale"/>
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script setup>
import {ref} from "vue";

import Modal from "@/components/Modal";

let titolo = ref('ciao12')
let name = ref(null)
let header =ref("Signup for the Giveaway!")
let text = ref('Grab your ninja swag for half price!')
let showModal = ref(false)

function toggleModal(){
  console.log("TOGGLE MODAL",showModal)
  showModal.value = !showModal.value
}
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
