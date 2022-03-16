<script setup>
import {ref} from "vue"
import axios from "axios"
const res = await axios.get("https://jsonplaceholder.typicode.com/posts")
const posts = ref(res.data)
console.log(res);
</script>
<template>
  <p>This is Home </p>
  <div v-for="post in posts" :key="post.id">
    <h2>{{post.title}}</h2>
    <p>{{post.body}}</p> 
  </div>
</template>

