<template>

 <div class="stage">
  <h1>{{ title }}<br>
   <span class="outline">{{ description }}</span>
  </h1>
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

  .stage {
    display: flex;
    width: 100%;
    max-width: 870px;
    margin: 0 auto var(--space-xxl) auto !important;
    padding: 0 0 0 0 !important;
  }

</style>
