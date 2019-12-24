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
    
      <svg xmlns="http://www.w3.org/2000/svg">
        <text>{{ post.frontmatter.title }}</text>
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


svg{

}

text{
  fill: none;
  stroke: black;
  stroke-width:0.5px;
  // stroke-dasharray: 2,2;
  stroke-linejoin: round;
}


</style>
