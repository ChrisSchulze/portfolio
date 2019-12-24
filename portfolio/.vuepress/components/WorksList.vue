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
        <svg width="800px" height="500px">
        <text y="0">{{ post.frontmatter.title }}</text>
        <text y="140" extent="870">{{ post.frontmatter.description }}</text>
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
    height: 900px;
    background: rgba(255,255,255, 1);
    margin-bottom: 5vw;
    cursor: pointer;
  }
  
  .info {
    position: absolute;
    top: 0;
    left: 0;
  }
  
text{
  fill: none;
  stroke: black;
  stroke-width:0.5px;
  stroke-linejoin: round;
  font-size: 100px;
}

</style>
