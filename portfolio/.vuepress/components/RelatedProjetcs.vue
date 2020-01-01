<template>
  <div class="header">
        <h3>More Projects</h3>
        <p>{{ project_name }}</p>
  </div>
</template>

<script>
  export default {
      year: {
        project_name: String,
        required: true
      },
  }
</script>

<style scoped>

  .header {
    display: flex;
    padding: 2rem 0;
    width: 100%;
    max-width: 600px;
    margin: 0 auto 0 auto;
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

</style>
