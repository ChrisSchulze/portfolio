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
        <svg viewBox="0 0 450 50">
        <text y="40">{{ post.frontmatter.title }}</text>
        <text y="40">{{ post.frontmatter.description }}</text>
        </svg>

        <h2>{{ post.frontmatter.title }}</h2>
        <span>{{ post.frontmatter.description }}</span>
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
    background: rgba(255,255,255, 1);
    margin-bottom: 5vw;
    cursor: pointer;
  }

  .info {
    position: absolute;
    left: 0;
    top: 2rem;
    padding: 0.5rem 1rem;
    max-width: 400px;
  }

  .info h2 {
    display: inline-block;
    width: auto;
    font-size: 0.8rem;
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

text{
  fill: none;
  stroke: black;
  stroke-width:0.5px;
  stroke-linejoin: round;
  font-size: 100px;
}

</style>
