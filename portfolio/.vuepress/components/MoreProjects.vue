<template>
    <div>
        <div>
            <h3>All Projects</h3>
        </div>
        
        <div class="all-projects">
            <div class="container">
        
                <router-link 
    	            tag="div"
      	            :to="post.path"
      	            v-for="post in posts"
      	            :key="post.title"
      	            class="project"
      	            >
                <h2>{{ post.frontmatter.title }}</h2>
                </router-link>      
            
        </div>
        </div>
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

.all-projects {


}

.all-projects > .container {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  
  padding: 0;
  margin: 0;
  list-style: none;
}
.project {
  flex: 1;
  display: block;
  padding: 2rem;
  text-decoration: none;
  border-top: 1px solid #d1d1d2;
  border-right: 1px solid #d1d1d2;
  border-bottom: 1px solid #d1d1d2;
  cursor: pointer;
}
.project:hover {
    background: #3d3d3d;
}
.project:last-of-type {
    border-right: 0px;
}
</style>
