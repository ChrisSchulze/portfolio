<template>
  <div class="project-list">

    <router-link
      :to="post.path"
      tag="div"
      v-for="post in posts"
      :key="post.title"
      class="post"
    >

<div class="svg-container">
	<svg version="1.1" viewBox="0 0 870 600" preserveAspectRatio="xMinYMin meet" class="svg-content">
        <text y="90">{{ post.frontmatter.title }}</text>
        <text class="outline" y="180" extent="870">{{ post.frontmatter.description }}</text>
	<text class="outline" y="270" extent="870">{{ post.frontmatter.description_second_line }}</text>
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
    height: 60vh;
    padding-top: 0;
    margin-bottom: 5vw;
    cursor: pointer;
  }
  
  .svg-container { 
	  display: inline-block;
	  position: relative;
	  width: 100%;
	  padding-bottom: 100%; 
	  vertical-align: middle; 
	  overflow: hidden;
    }
    
  .svg-content { 
	  display: inline-block;
	  position: absolute;
	  top: 0;
	  left: 0;
    }  
  
  text {
    fill: none;
    stroke: #D1D1D2;
    stroke-width:0.5px;
    stroke-linejoin: round;
    font-size: 90px;
  }

</style>
