<template>
  <span class="text">{{ $site.themeConfig.footer }}</span>
  
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


    <nav v-if="navLinks" class="navigation right desktop-nav">
      <ul>
        <router-link
          v-for="nav in navLinks"
          :key="nav.text"
          v-if="nav.position === 'right' && !nav.external"
          tag="li"
          :to="nav.link"
          active-class="active"
          v-text="nav.text"
          exact
        />
        <li v-for="nav in navLinks" v-if="nav.position === 'right' && nav.external">
          <a :href="nav.link" target="_blank">{{ nav.text }}</a>
        </li>
      </ul>
    </nav>
 </div>
 
</template>

<script>
  export default {
    props: {
      logo: {
        type: String,
        required: false,
      },
      sticky: {
        type: Boolean,
        required: false,
      }
    },
    data() {
      return {
        mobileNavActive: false
      }
    },
    computed: {
      navLinks() {
        return this.$site.themeConfig.nav
      },
    },
    methods: {
      toggleMobileNav() {
        this.mobileNavActive = !this.mobileNavActive
      }
    }
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
