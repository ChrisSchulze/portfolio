<template>
  <div class="project-list">

    <router-link
      :to="post.path"
      tag="div"
      v-for="post in posts"
      :key="post.title"
      class="post"
    >

    <h1>{{ post.frontmatter.title }}<br>
    <span class="outline">{{ post.frontmatter.description }} &#10132;</span>
    </h1>
        
    </router-link>

  </div>
</template>

<script>
  export default {
    computed: {
      posts() {
        return this.$site.pages
          .filter(x => x.path.startsWith('/works/') && !x.frontmatter.works_index)
          .sort((a, b) => new Date(b.frontmatter.date) - new Date(a.frontmatter.date))
      }
    }
  }
</script>

<style scoped>

  .post {
    position: relative;
    width: 100%;
    height: 60vh;
    padding-top: 0;
    margin-bottom: 5vw;
    cursor: pointer;
  }

</style>
