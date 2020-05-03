<template>
  <footer class="footer" >  

      <column class="text">
        <h1 class="lead">Let’s create something valuable together.</h1>
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
    

    margin-bottom: var(--spacing-medium);
  }
  
  .text {
  justify-self: center;
  flex-grow: 2;
  }
  
    .logo {
  justify-self: end;
  flex-grow: 1;
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

  .nav li:last-of-type {
    margin: 0;
  }
  .nav li:hover {
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
