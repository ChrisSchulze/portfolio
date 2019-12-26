<template>

 <div class="header">
<h1>
{{ title }}
<span class="outline">{{ description }}</span>
</h1>
  </div>

<div class="content custom" :img src="{{ `url(${post.frontmatter.thumbnail})` }}">

      <div class="info">
        <h2>{{ post.frontmatter.title }}</h2>
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span>
      </div>

</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      description: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>

  .header {
    display: flex;
    padding: 2rem 0;
    width: 100%;
    max-width: 800px;
    margin: 0 auto 3rem auto;
  }

  .column {
    flex: 0 0 33.33%;
  }

  .label {
    margin-bottom: 0.5rem;
    font-weight: 700;
  }

  .value {
    font-weight: 400;
  }

  .categories:after {
    content: ', ';
  }

  .categories:last-of-type:after {
    content: '';
  }
  
    .picture {
    width: 20px;
    height: auto;
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
      font-size: 90px;
      fill: #D1D1D2;
      text-rendering: geometricPrecision;
      }
      
  .outline {
    fill: none !important;
    stroke: #D1D1D2;
    stroke-width:0.5px;
    stroke-linejoin: round;
  }

</style>
