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
  max-width: 870px;
}

.all-projects > .container {
    display: flex;
    width: 100%;
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: nowrap; /* Safari 6.1+ */
    flex-wrap: nowrap;
}
.project {
  flex: 1;
  display: block;
  padding: 2rem;
  text-decoration: none;
  border-bottom: 1px solid #d1d1d2;
}



</style>
