<template>
    <div id="post-container">
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
    #post-container {
        margin: 0 auto;
    }

    #post-container img {
        max-width: 80%;
        max-height: 800px;
        margin: 0 auto;
        border: 1em solid rgba(0, 0, 0, 0.7);
    }

    #post-container h1 {
        text-align: center;
    }

    #post-container p {
        text-align: center;
    }
</style>