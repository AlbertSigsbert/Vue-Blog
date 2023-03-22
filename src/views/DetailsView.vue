<template>
  
    <div v-if="error">{{ error }}</div>
    <div v-if="post" class="post">
        <h3>{{post.title}}</h3>
        <p>{{ post.body }}</p>
        <span v-for="tag in post.tags" :key="tag" class="tag">#{{ tag }}</span>
    </div>
    <div v-else>
      <p>Loading...</p>
    </div>
  
</template>

<script>
import getPost from '@/composables/getPost'
export default {
 props:['id'],
 setup(props){
   const {post,error,load} = getPost(props.id)

   load()

   return {post,error}
 }
}
</script>

<style>
.post {
  margin: 6rem 8%;
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
</style>