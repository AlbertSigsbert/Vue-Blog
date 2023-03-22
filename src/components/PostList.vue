<template>
  <div class="blog-posts">
    <div v-for="post in posts" :key="post.id">
      <SinglePost :post="post" />
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from 'vue';
import SinglePost from "./SinglePost.vue";
export default {
  props: ["posts"],
  components: { SinglePost },
  setup(props) {
    onMounted(()=> {
        console.log('PostList mounted')
    })
    onUnmounted(() => {
        console.log('PostList unmounted');
    })
    onUpdated(() => {
        console.log('PostList updated')
    })
  },
};
</script>

<style>
</style>