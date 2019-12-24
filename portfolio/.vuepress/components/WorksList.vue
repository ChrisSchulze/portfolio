<template>
  
  <div class="project-list">
  
    <router-link
      :to="post.path"
      tag="div"
      v-for="post in posts"
      :key="post.title"
      class="post"    
      >
      <svg viewBox="0 0 450 50">
        <h1>{{ post.frontmatter.title }}</h1>
        <text y="40"> {{ post.frontmatter.description }}</text>
      </svg>
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
    font-size: 4rem;
    font-weight: 700;
    margin: 0;
  }

  .info span {
    display: inline-block;
    width: auto;
    margin: 0;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke: 1px #D1D1D2;
  }

svg{
  width: 100%;
  height: 120px;
}

text{
  fill: none;
  stroke: white;
  stroke-width:0.5px;
  // stroke-dasharray: 2,2;
  stroke-linejoin: round;
}

</style>
