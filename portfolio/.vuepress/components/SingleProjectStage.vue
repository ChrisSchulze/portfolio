<template>

 <div class="header">
  <h1>{{ title }}<br>
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
    width: 100%;
    max-width: 870px;
    margin: 0 auto 0 auto !important;
    padding: 0 0 0 0 !important;
  }

  .column {
    flex: 0 0 33.33%;
  }

  .label {
    margin-bottom: 0.5rem;
    font-weight: 700;
  }

  .value {
    font-size: 0.6rem;
    line-height: 0.75rem;
    letter-spacing: 0.75px;
    font-weight: 700;
    color: #d1d1d2 !important;
    margin: 0 auto 0 auto;
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

</style>
