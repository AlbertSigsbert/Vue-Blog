<template>
  <div class="home">
    <h1>Blogs</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>
      <p>Loading...</p>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import PostList from "@/components/PostList.vue";

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([]);
    const error = ref(null);

    const load = async () => {
      try {
        const res = await fetch("http://localhost:3000/posts");
        if (!res.ok) {
          throw Error("Response not available");
        }
        posts.value = await res.json();
      } catch (err) {
        error.value = err.message;
        console.log(error.value);
      }
    };

    load();

    return { posts, error };
  },
};
</script>
