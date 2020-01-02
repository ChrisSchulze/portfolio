<template>

  <div class="description">

    <div class="column-big">
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
    max-width: 870px;
    
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: wrap; /* Safari 6.1+ */
    flex-wrap: wrap;
    
    margin: 0 auto 0 auto;
    padding-bottom: var(--padding-xsmall);
  }
  
  .description > * {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 220px;
  padding-bottom: var(--padding-xsmall);
}

  .label {
    margin-bottom: 0.25em;
    font-weight: 700;
  }
  
  .value {
    font-weight: 400;
    font-size: 1em;
    line-height: 1.5em;
    letter-spacing: 1.25px;
    margin: auto auto auto auto;
  }
  
  @media (max-width: 900px) {
      .value {
          font-size: 0.75em;
          line-height: 1em;
        }
  }
  
  @media (max-width: 400px) {
      .value { 
          font-size: 0.75em;
          line-height: 0.75em;
        }
  }

  .categories:after {
    content: ', ';
  }

  .categories:last-of-type:after {
    content: '';
  }

</style>
