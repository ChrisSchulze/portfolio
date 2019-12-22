<template>

  <div class="header">
    <div class="column">
      <span class="value">{{ title }}</span>
    </div>
    <div class="column">
      <span class="value">{{ description }}</span>
    </div>  
        <div class="column">
      <span class="value"><img src="{{ path }}" height="42" width="42"></span>
    </div>    
  </div>

<div       class="post"
      :style="{ backgroundImage: `url(${post.frontmatter.thumbnail})` }"
    >


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

</style>
