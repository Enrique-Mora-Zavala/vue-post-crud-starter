<script setup>
import axios from 'axios'
//import { defineProps } from 'vue'
import { RouterLink, useRouter } from 'vue-router'

const router = useRouter()

defineProps({
  post: Object,
})

const deletePost = async (postId) => {
  try {
    const confirm = window.confirm('Are you sure you want to delete this posts?')
    if (confirm) {
      await axios.delete(`http://localhost:8080/posts/${postId}`)
      router.push('/')
    }
  } catch (error) {
    console.error('Error deleting post: ', error)
  }
}
</script>
<template>
  <td>{{ post.id }}</td>
  <td>{{ post.title }}</td>
  <td>
    <RouterLink :to="`/posts/${post.id}`" class="btn btn-green">👁️</RouterLink>
    <RouterLink :to="`/posts/edit/${post.id}`" class="btn btn-blue">✏️</RouterLink>
    <button @click="deletePost(post.id)" class="btn btn-red">🗑️</button>
  </td>
</template>
