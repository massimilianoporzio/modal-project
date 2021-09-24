<template>
 <div class="backdrop">
   <div class="modal" :class="{sale: theme === 'sale'}">
     <h1>{{ header }}</h1>
     <p>{{text}}</p>
   </div>
 </div>
</template>

<script setup>
import {defineProps} from "vue";

const props = defineProps({
  header: String,
  text: String,
  theme: String
})
</script>

<style>
  .modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  }
  .backdrop{
  top: 0;
  left:0;
  position: fixed;
  background: rgba(0,0,0,0.5);
  width: 100%;
  height: 100%;
  }
  .modal h1 {
    color: seagreen;
    border: none;
    padding: 0;
  }
  .modal p {
    font-style: normal;
  }
  .modal.sale {
    background: crimson;
    color: white;
  }
  .modal.sale h1 {
    color: white;
  }
</style>