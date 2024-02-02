<template>
  <router-link :to="{ name: 'Details', params : {id: post.id }}">
    <h1>{{ post.title }}</h1>
  </router-link>
  <p>{{ snippet }}</p>
  <span v-for="tag in post.tags" :key="tag.id">
   # {{ tag }}
  </span>
</template>

<script>
import { computed } from 'vue'
export default {
    props: ['post'],
    setup(props){
        const snippet = computed(() =>{
            return props.post.body.substring(0,200) + '......'
        })

        return { snippet }
    }
}
</script>

<style>

</style>