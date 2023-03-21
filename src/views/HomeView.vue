<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and my age is {{age}}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add Age By 1</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup(){
    let name = ref('John')
    let age = ref(25)

   const p = ref(null);


    const handleClick = () => {
      // p.value.textContent = "Hello,World";
      name.value = "Mario"
    }

    return {name,age, handleClick, p}
  }
 
}
</script>
