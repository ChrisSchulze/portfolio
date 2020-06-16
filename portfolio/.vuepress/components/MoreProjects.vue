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
                <h3>{{ post.frontmatter.title }}</h3>
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
  /* We first create a flex layout context */
  display: flex;
  
  /* Then we define the flow direction 
     and if we allow the items to wrap 
   * Remember this is the same as:
   * flex-direction: row;
   * flex-wrap: wrap;
   */
  flex-flow: row wrap;
  
  /* Then we define how is distributed the remaining space */
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
  border-bottom: 1px solid #d1d1d2;
}



</style>
