<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add Age By 1</button>
    <input type="text" v-model="name" />

    <h2>Reactive</h2>
    <p>Ninja one is {{ninjaOne.name}} and is {{ninjaOne.age}} years old</p>
    <button @click="updateNinja">Update Ninja</button>
  </div>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "HomeView",
  setup() {
    let name = ref("John");
    let age = ref(25);

    const ninjaOne = reactive({ name: "Shinsuke", age: 25 });
    const p = ref(null);

    const handleClick = () => {
      // p.value.textContent = "Hello,World";
      name.value = "Mario";
    };
    const updateNinja = () => {
      // p.value.textContent = "Hello,World";
      ninjaOne.name = "Matsura";
    };

    return { name, age, handleClick, p, updateNinja, ninjaOne };
  },
};
</script>
