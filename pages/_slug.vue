<template>
    <div id="posts-container">
        <h1>{{ posts.title }}</h1>
        <img :src= "posts.image" alt="posts.slug"/>
        <nuxt-content :document= "posts" />
        
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
      const posts = await $content('posts', params.slug).fetch()

      return { posts }
    }
  }
</script>

<style>
    img {
        max-width: 80%;
        max-height: 800px;
        margin: 0 auto;
        border: 1em solid rgba(0, 0, 0, 0.7);
    }

    h1 {
        text-align: center;
    }

    p {
        text-align: center;
    }
</style>