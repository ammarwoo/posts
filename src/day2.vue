<script setup>
import HelloWorld from './components/HelloWorld.vue'

import {ref} from 'vue'
let count=ref(0);
function increment () {
  count.value +=1

}
function decrement(){
  count.value -=1
}

</script>


<template>

  <div>
    <h1>welcome </h1>
    <p>{{ count }}</p>
    <button @click="increment">Increment</button>
    <br>
    <br>
    <button @click="decrement">Decrement</button>
  </div> 
  
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
