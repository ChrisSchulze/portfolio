<template>
  <footer class="footer" >  
      <column class="nav">
        <div id="div_top_hypers">
          <ul id="ul_top_hypers">
            <li><a href="/" class="a_top_hypers">Work</a></li>
            <li><a href="mailto:jan.christian.schulze@gmail.com" class="a_top_hypers">Contact</a></li>
          </ul>
        </div>
      </column>
      <column class="text">
        <p class="hero">I'm always happy to meet new people. Give me a call <a class="contact" href="tel:+49-1157-39240">+49 1157 39 240 376</a> or send me an <a href="mailto:jan.christian.schulze@gmail.com" class="contact">email.</a></p>
      </column>
      <column class="logo">
        <img class="small" src="/upload/logo.png">
      </column>
  </footers>
</template>

<style scoped>

  .footer {
    display: flex;
    display: -webkit-flex; /* Safari */
    -webkit-flex-wrap: wrap; /* Safari 6.1+ */
    flex-wrap: wrap;
    justify-content: space-between;
    width: 100%;

    font-weight: 400;
    padding-bottom: var(--padding-big);
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

#div_top_hypers {
    background-color:#eeeeee;
    display: inline;      
}
#ul_top_hypers li{
    font-size: 0.75em !important;
    padding-right: 0.5em;
    display: inline;  
}

  #ul_nav li {
    
    display: inline;
    list-style-type: none !important;
    user-select: none;
    cursor: pointer;
    border-bottom: 1px solid transparent;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

</style>
