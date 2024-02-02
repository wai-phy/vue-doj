<template>
  <div class="home">
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>
      <p>Loading ......</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import PostList from '@/components/PostList.vue';
import getPosts from '@/composables/getPosts.js'
export default {
  name: 'HomeView',
  components: { PostList },
  setup() {
      const {posts, error, load} = getPosts()

      load()
    return { posts, error}
  }
}
</script>
