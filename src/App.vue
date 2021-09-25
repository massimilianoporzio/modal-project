<template>

  <h1>{{titolo}}</h1>
  <teleport to="#modal" v-if="showModal">
    <Modal theme="sale"  @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sing up now</a>
        <a href="#">Info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>
  <teleport to="#modal" v-if="showModalTwo">
    <Modal @close="toggleModalTwo"><h2>Hello</h2></Modal>
  </teleport>
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal Two</button>
</template>

<script setup>
import {ref} from "vue";

import Modal from "@/components/Modal";

let titolo = ref('ciao12')
let name = ref(null)
let header =ref("Signup for the Giveaway!")
let text = ref('Grab your ninja swag for half price!')
let showModal = ref(false)
let showModalTwo = ref(false)

function toggleModal(){
  showModal.value = !showModal.value
}
function toggleModalTwo(){
  showModalTwo.value = !showModalTwo.value
}
function  handleClick(e)
{
  const el = name.value
  el.classList.add('active')
  el.focus()
}
</script>



<style>
#app, #modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
