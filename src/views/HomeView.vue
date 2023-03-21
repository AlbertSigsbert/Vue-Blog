<template>
  <div class="home">
    <h1>Home</h1>
    <p>My name is {{ name }} and my age is {{age}}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  setup(){
    let name = 'John'
    let age = 25

    const handleClick = () => {
      console.log('CLICKED');
    }

    return {name,age, handleClick}
  }
 
}
</script>
