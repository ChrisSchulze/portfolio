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
    <h1>{{ post.frontmatter.title }}</h1>
      <svg xmlns="http://www.w3.org/2000/svg">
        <text>{{ post.frontmatter.description }}</text>
      </svg>
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
    margin-bottom: 5vw;
    cursor: pointer;
    background-color: red;
  }

  .info {
    position: absolute;
    left: 0;
    top: 0;
    background: rgba(255,255,255, 1);
    
  }

text {
  fill: none;
  stroke: #0000FF;
  stroke-width:0.25px;

}



</style>
