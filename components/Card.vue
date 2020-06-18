<template>
  <div class="card">
    <h1>{{ cardTitle }}</h1>
    <p>{{ content }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed, ref } from '@vue/composition-api'
import Post from '@/models/Post'

export default defineComponent({
  props: {
    post: {
      type: Object as () => Post,
      required: true
    }
  },

  setup ({ post }) {
    const cardTitle = computed(() => `${post.id} - ${post.title}`)
    const content = post.content

    return {
      cardTitle,
      content
    }
  }
})
</script>

<style>
.card {
  border-radius: 12px;
  border: 1px solid #dedede;
  color: #454545;
  padding: 12px 20px;
  background-color: white;
}
</style>
