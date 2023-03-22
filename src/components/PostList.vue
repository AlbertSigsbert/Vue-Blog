<template>
  <div class="blog-posts">
    <div v-for="post in posts" :key="post.id">
      <SinglePost :post="post" />
    </div>
  </div>
</template>

<script>
import SinglePost from "./SinglePost.vue";
export default {
  props: ["posts"],
  components: { SinglePost },
  setup(props) {
  },
};
</script>

<style>
.blog-posts {
  margin: 2rem 6%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 30px;
}
.blog-posts .blog-post{
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.2);
}

.blog-posts a {
  color: #333;
  text-decoration: none;
}
.blog-posts a:hover {
  cursor: pointer;
  color: #8b8b8b;
}
.blog-posts h2 {
  font-size: 18px;
  margin-bottom: 10px;
}

.blog-posts p {
  font-size: 16px;
  margin-bottom: 10px;
}

.tag {
  display: inline-block;
  font-size: 14px;
  font-weight: bold;
  background-color: #f2f2f2;
  padding: 5px 10px;
  margin-right: 10px;
  margin-bottom: 10px;
  color: #333;
  border-radius: 5px;
}

.tag:hover {
  background-color: #e0e0e0;
  color: #000;
}
@media screen and (max-width: 767px) {
  .blog-posts {
    grid-template-columns: repeat(1, 1fr);
  }
}

</style>