<template>
  <footer class="footer" >  
      <column id="nav">
        <div id="div_top_hypers">
          <ul id="ul_top_hypers">
            <li><a href="/" class="a_top_hypers">Work</a></li>
            <li><a href="mailto:jan.christian.schulze@gmail.com" class="a_top_hypers">Contact</a></li>
          </ul>
        </div>
      </column>
      <column>
        <p class="hero">I'm always happy to meet new people. Give me a call <span class="contact">+49 1157 39 240 376</span> or send me an <span class="contact">email.</span></p>
      </column>
      <column>
        <img class="logo" src="/upload/logo.png">
      </column>
  </footers>
</template>

<style scoped>

  .footer {
    display: flex;
    justify-content: space-between;
    width: 100%;
    font-size: 0.8rem;
    font-weight: 400;

  }
  
  .hero {
  padding-bottom: 0px !important;
  }
  
  .hero .contact {
  color: #333333; }
  
  .logo {
  margin: 0 0 0 0;
  }

#div_top_hypers {
    background-color:#eeeeee;
    display:inline;      
}
#ul_top_hypers li{
    display: inline;
    margin-right: 1rem;
}

  #ul_nav li {
    display: inline;
    list-style-type: none !important;
    margin-right: 1rem;
    user-select: none;
    cursor: pointer;
    border-bottom: 1px solid transparent;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

</style>
