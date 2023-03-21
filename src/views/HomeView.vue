<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and my age is {{age}}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup(){
    let name = 'John'
    let age = 25

   const p = ref(null);


    const handleClick = () => {
      console.log('CLICKED');
      p.value.textContent = "Hello,World";
    }

    return {name,age, handleClick, p}
  }
 
}
</script>
