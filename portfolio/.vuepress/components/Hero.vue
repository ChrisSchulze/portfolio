<template>
  <h1 v-if="text" class="title" v-html="text" />
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped>
  .title {
    font-family: "PilatWideDemi";
    text-align: center;
    width: 800px;
    max-width: 100%;
    font-size: var(--space-l);
    line-height: var(--space-l);
    font-weight: 700;
    color: #D1D1D2; 
    margin: 0 auto 0 auto;
  }



</style>
