<template>
 <div class="backdrop" @click.self="closeModal">
   <div class="modal" :class="{sale: theme === 'sale'}">
     <slot>default slot</slot>
     <div class="actions">
       <slot name="links"></slot>
     </div>
   </div>
 </div>
</template>

<script setup>
import {defineProps, defineEmits} from "vue";
const emits = defineEmits(["close"])

function closeModal() {
  console.log("closeModal")
  emits('close')
}
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

  .modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
  }
  .modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
  }
  .modal.sale {
    background: crimson;
    color: white;
  }
  .modal.sale h1 {
    color: white;
  }
  .modal.sale .actions{
    color: white;
  }
  .modal.sale .actions a {
    color: white;
  }
</style>
