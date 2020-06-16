<template>
    <div>
        <div class="latest-journals-heading container">
            <h3>All Projects</h3>
        </div>
        
        <div class="latest-journals">
            <div class="container">
        
                <router-link 
    	            tag="div"
      	            :to="post.path"
      	            v-for="post in posts"
      	            :key="post.title"
      	            class="journal"
      	            >
                <h3 class="journal-title">{{ post.frontmatter.title }}</h3>
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

.latest-journals-heading {
  margin-top: 6rem;
  margin-bottom: 1rem;
}
.latest-journals {
  max-width: 100%;
  margin: 0 2rem;
  border: 1px solid #d1d1d2;
}
.latest-journals > .container {
    display: flex;
    width: 100%;
    max-width: 870px;
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: wrap; /* Safari 6.1+ */
    flex-wrap: wrap;
}
.journal {
  flex: 0 0 100%;
  display: block;
  padding: 2rem;
  transition: background 0.25s ease;
  text-decoration: none;
  border-bottom: 1px solid #d1d1d2;
}

.journal:last-of-type {
  border-bottom: 0;
}

.journal:hover {
  background: #3d3d3d;
}

.journal-title {
  font-size: 1rem;
  line-height: 1.35;
}

</style>
