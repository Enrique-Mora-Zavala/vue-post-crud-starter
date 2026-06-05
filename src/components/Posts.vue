<script setup>
import { RouterLink } from 'vue-router'
import Post from '@/components/Post.vue'
</script>

<template>
  <div class="center-container">
    <h1>All Post</h1>
    <RouterLink :to="`/`" class="btn btn-blue">Go to Home</RouterLink>
    <br />
    <br />
    <table id="posts">
      <tr>
        <th>S.N</th>
        <th>Title</th>
        <th>Action</th>
      </tr>
      <Post />
    </table>
  </div>
</template>
