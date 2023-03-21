<template>
  <div class="home">
    <h1>Names</h1>
    <input type="text" placeholder="Search a name" v-model="search">
    <p>Searched text - {{search}}</p>
   <div v-for="name in matchedNames" :key="name">{{name}}</div>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "HomeView",
  setup() {
    const search = ref('')
    const names = ref(['Ava', 'Liam', 'Emma', 'Noah', 'Olivia', 'William', 'Sophia', 'Elijah', 'Isabella', 'James']);
    
    //Computed properties
    const matchedNames = computed(() => {
      return names.value.filter(name => name.includes(search.value))
    })

    return { names, search, matchedNames};
  },
};
</script>
