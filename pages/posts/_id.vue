<template>
<div class="posts">
  <section class="container mx-auto pt-8 px-2">
    <div class="title p-5">
      <h1>Que posición juegas?</h1>
    </div>
    <div class="description p-5">
      <h2>{{ post.title}}</h2>
      <p>{{ post.content }}</p>
    </div>
  </section>
  <aside class="container mx-auto p-5">
    <ul>
      <li v-for="related in relatedPosts">
        <nuxt-link :to="{name: 'posts-id', params: {id: related.id}}">
          {{related.title}}
        </nuxt-link>
      </li>
    </ul>
  </aside>
</div>
</template>
<script>
export default {
  head() {
    return {
      title: this.post.title,
      meta: [
        { name: 'twitter-title', content: this.post.title},
        { name: 'twitter-description', content: this.post.content},
        { name: 'twitter-image', content: 'https://picsum.photos/200'},
        { name: 'twitter-card', content: 'summary_large_image'}
      ]
    }
  },
  data() {
    return {
      id: this.$route.params.id,
    }
  },
  computed: {
    post() {
      return this.$store.state.posts.all.find(post => post.id === this.id)
    },
    relatedPosts() {
      return this.$store.state.posts.all.filter(post => post.id !== this.id)
    }
  },
}
</script>
<style scoped>
h1 {
  font-size: 2rem;
  color: salmon;
  margin-bottom: 0.5rem;
}
h2 {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}
p {
  text-align: justify;
  max-width: 500px;
}
.posts {
  display: flex;
}
section {
  widows: 70%;
  float: left;
}
aside {
  width: 30%;
}
ul li a {
  color: salmon;
  text-align: left;
}
</style>