<template>

  <div class="header">
    <div class="column">
      <span class="value">{{ title }}</span>
    </div>
    <div class="column">
      <span class="value">{{ description }}</span>
    </div>  
  </div>

<div class="StageImage">

<span class="value"><img src="{{ path }}" height="42" width="42"></span>
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

</style>
