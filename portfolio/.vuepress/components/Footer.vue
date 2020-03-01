<template>
  <footer class="footer" >  
      <column class="nav">
      <ul>
        <router-link
          v-for="nav in navLinks"
          :key="nav.text"
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
      </column>
      <column class="text">
        <p class="hero">I'm always happy to meet new people. Give me a call <a class="bold" href="tel:+49-157-39240">+49 157 39 240 376</a> or send me an <a href="mailto:jan.christian.schulze@gmail.com" class="bold">E-Mail.</a></p>
      </column>
      <column class="logo">
        <img class="small" src="/upload/logo.png">
      </column>
  </footers>
</template>

<script>
  export default {
     
    computed: {
      navLinks() {
        return this.$site.themeConfig.nav
                  }
               }
                }
</script>

<style scoped>

  .footer {
    display: flex;
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: wrap; /* Safari 6.1+ */
    flex-wrap: wrap;
    justify-content: space-between;
    width: 100%;
    font-weight: 400;
    margin-bottom: var(--spacing-medium);
  }
  
  .nav {
  justify-self: start;
  }
  
  .text {
  justify-self: center;
  }
  
    .logo {
  justify-self: end;
  }
  
  @media (max-width: 900px) {
      .nav, .text, .logo { 
    padding-bottom: var(--padding-xsmall);
        }
  }
  
  @media (max-width: 400px) {
      .nav, .text, .logo { 
    padding-bottom: var(--padding-xsmall);
        }
  }
  
    .hero {
  padding-bottom: 0px !important;
  }
  
  .hero .contact {
  color: #333333; 
  }
  
  .small {
  margin: 0 0 0 0;
  width: 80px;
  height: auto;
  align: right;
  padding-top: 4px;
  padding-bottom: 0px !important;
  }



  .navigation li {
    display: inline-block;
    list-style: none !important;
    margin-right: 1rem;
    user-select: none;
    cursor: pointer;
    border-bottom: 1px solid transparent;
  }
  .navigation li:last-of-type {
    margin: 0;
  }
  .navigation li:hover {
    border-bottom: 1px solid #D1D1D2;
  }
  .active {
    border-bottom: 1px solid #D1D1D2;
  }
  a {
    text-decoration: none;
    color: inherit;
  }
  a:active { color: inherit; }
  a:visited { color: inherit; }


</style>
