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
      <column>
        <p class="hero">I'm always happy to meet new people. Give me a call <span class="contact">+49 1157 39 240 376</span> or send me an <span class="contact">email.</span></p>
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
  
  
  .footer > * {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 320px;
}
  
  
  .hero {
  padding-bottom: 0px !important;
  }
  
  .hero .contact {
  color: #333333; 
  }
  
  .nav {
  justify-self: start;
  }
  
    .logo {
  justify-self: end;
  }
  
  .small {
  margin: 0 0 0 0;
  width: 80px;
  height: auto;
  align: right;
  padding-bottom: 0px !important;
  }

#div_top_hypers {
    background-color:#eeeeee;
    display:inline;      
}
#ul_top_hypers li{
    display: inline;
    
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
