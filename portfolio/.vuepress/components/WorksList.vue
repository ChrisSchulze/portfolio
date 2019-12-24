<template>
  <div class="project-list">

    <router-link
      :to="post.path"
      tag="div"
      v-for="post in posts"
      :key="post.title"
      class="post"
      
    >

      <div class="info">
        <h1>{{ post.frontmatter.title }}
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span></h1>
      </div>

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
    padding-top: 56.25%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    margin-bottom: 5vw;
    cursor: pointer;
  }

  .info {
    position: absolute;
    left: 0;
    top: 0;
    padding: 0.5rem 1rem;
    
    max-width: 400px;
  }

  .info h1 {
    display: inline-block;
    width: auto;
    font-size: 1.6rem;
    font-weight: 700;
    margin: 0;
  }

  .info span {
    display: inline-block;
    width: auto;
    margin: 0;
    margin-left: 0.5rem;
    font-size: 0.8rem;
  }

</style>
