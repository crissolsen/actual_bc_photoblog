<template>
  <div id="posts-container">
    <div class="posts" v-for= "post in posts" :key= "post.slug" :style= "{ backgroundImage: `url(${post.image})`, backgroundSize: 'cover'}">
      <nuxt-link :to="`/${post.slug}`" > <h3>{{ post.title }}</h3> </nuxt-link>
    </div>
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
  #posts-container {
    display: flex;
    flex-direction: column;
    flex: 1 1 300px;
  }

  .posts {
    height: 15vmax;
    margin: 0.3em;
    border-radius: 1em;
    /* border: 0.15em solid black; */

  }

  .posts:hover {
    animation: grow 3s forwards;
  }

  @keyframes grow {
    100% {
      height: 30vmax;
    }
  }

  .posts h3 {
    font-size: 1.5em;
    background-color: rgba(0, 0, 0, 0.7);
    color: white;
    border-radius: 0.2em;
    text-align: center;
    padding: 0.3em;
    font-family: 'Abril Fatface', serif;
    margin: 0.3em;
  }
</style>
