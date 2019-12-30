<template>
  <span class="text">{{ $site.themeConfig.footer_headline }}</span>
  


 
</template>

<script>
  export default {
    computed: {
      navLinks() {
        return this.$site.themeConfig.nav
      },
    },
  }
</script>

<style scoped>
  .text {
    display: block;
    font-size: 0.8rem;
    text-align: left;
    padding: 4rem 5vw;
  }
</style>
