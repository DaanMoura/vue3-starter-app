<template>
  <div class="container">
    <card :post="post" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Card from '@/components/Card.vue'
import Post from '@/models/Post'

export default Vue.extend({
  components: {
    Card
  },
  data () {
    const post: Post = {
      id: 0,
      title: 'Testing Composition API',
      content: 'Also using typescript'
    }

    return {
      post
    }
  }
})
</script>

<style>
.container {
  padding: 3rem 12rem;
}
</style>
