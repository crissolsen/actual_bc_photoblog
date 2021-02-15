<template>
  <div id="posts-container">
    <div class="posts" v-for= "post in posts" :key= "post.slug" :style= "{ backgroundSize: 'cover'}">
      <nuxt-link :to="`/${post.slug}`" > <h3>{{ post.title }}</h3> 
      <div class="imgContainer" :style= "{backgroundImage: `url(${post.image})`}">

      </div>
      
      </nuxt-link>
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
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
  }

  .posts {
    height: auto;
    margin: 1em;
    border-radius: 0 1em 0 0;
    /* border: 0.15em solid black; */
    background: white;
    min-width: 30%;

  }

  .posts:hover {
    background: black;
  }


  .posts h3 {
    font-size: 1.5em;
    background-color: black;
    color: white;
    text-align: center;
    padding: 0.3em;
    font-family: 'Open-sans', sans-serif;
    margin-top: 1em;
  }

  .imgContainer {
    height: 20vmax;
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    margin: 1em;
  }

</style>
