<template>
  <p>This is About </p>
  <div v-for="post in posts" :key="post.id">
    <h2>{{post.title}}</h2>
    <p>{{post.body}}</p> 
  </div>
</template>

<script>
import axios from "axios"
export default {
  data() {
    return {
      posts: []
    }
  },
  methods: {
    featchPosts() {
      axios.get("https://jsonplaceholder.typicode.com/posts").then((res)=>{
        this.posts=res.data
        console.log(this.posts);
      })
    }
  },
  mounted() {
    this.featchPosts()
  }
  
}
</script>