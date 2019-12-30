<template>
  <span class="text">{{ $site.themeConfig.footer_copy }}</span>
  
 <div>
    <nav v-if="navLinks" class="navigation left desktop-nav">
      <ul>
        <router-link
          v-for="nav in navLinks"
          :key="nav.text"
          v-if="nav.position === 'left' && !nav.external"
          tag="li"
          :to="nav.link"
          active-class="active"
          v-text="nav.text"
          exact
        />
        <li v-for="nav in navLinks" v-if="nav.position === 'left' && nav.external">
          <a :href="nav.link" target="_blank">{{ nav.text }}</a>
        </li>
      </ul>
    </nav>
</div>

 
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
