<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        Project_8
      </h1>
      <h2 class="subtitle">
        With Nuxt.js!
      </h2>
      <div class="links">
        <li v-for="post in posts" :key="post.id">
          <nuxt-link :to="{ name: 'posts-id', params: { id: post.id}}" :key="post.id" class="button--grey">
            {{post.title}}
          </nuxt-link>
        </li>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  head() {
    return {
      title: 'Home page',
      meta: [
        { name: 'twitter-title', content: 'Project_8 with Nuxt.js'},
        { name: 'twitter-description', content: 'This is a test app!'},
        { name: 'twitter-image', content: 'https://picsum.photos/200'},
        { name: 'twitter-card', content: 'summary_large_image'}
      ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
