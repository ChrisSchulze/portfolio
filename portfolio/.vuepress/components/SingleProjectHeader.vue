<template>

  <div class="description">

    <div class="column">
      <Label class="label">What we did</Label>
      <span class="value">{{ services }}</span>
    </div>

    <div class="column">
      <Label class="label">My Role</Label>
      <span class="value categories" v-for="category in categories" v-text="category" />
    </div>

    <div class="column">
      <Label class="label">Year</Label>
      <span class="value">{{ year }}</span>
    </div>

  </div>
</template>

<script>
  export default {
    props: {
      services: {
        type: String,
        required: true
      },
      year: {
        type: String,
        required: true
      },
      categories: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>

  .description {
    display: flex;
    width: 100%;
    max-width: 800px;
    
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: wrap; /* Safari 6.1+ */
    flex-wrap: wrap;
    
    margin: 0 auto 0 auto;
  }
  
  .description > * {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 160px;
  padding-bottom: var(--spacing-medium);
  padding-right: var(--padding-xsmall);
}

  .label {
    font-size: 0.8rem;
    line-height: 1.25rem;
    font-family: "PilatWideDemi" !important;
    letter-spacing: 1.2px;
    color: #d1d1d2;
  }
  
  .value {
    font-size: 0.8rem;
    line-height: 1.25em;
    letter-spacing: 1.2px;
    color: #7f7f7f;
    margin: auto auto auto auto;
  }
  
  @media (max-width: 900px) {
      .value {
          font-size: 0.85em;
          line-height: 1em;
        }
  }
  
  @media (max-width: 400px) {
      .value { 
          font-size: 0.85em;
          line-height: 0em;
        }
  }

  .categories:after {
    content: ', ';
  }

  .categories:last-of-type:after {
    content: '';
  }

</style>
