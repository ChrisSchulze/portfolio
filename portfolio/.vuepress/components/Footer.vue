<template>
  <footer class="footer" >
  
    <column id="nav">
    <ul id="links">
        <li><a href="" class="links">Work</a></li>
        <li><a href="" class="links">Contact</a></li>
    </ul>
    </column>
    
    <column>
      <p class="einleser">I'm always happy to meet new people. Give me a call <span class="contact">+49 1157 39 240 376</span> or send me an <span class="contact">email.</span></p>
    </column>
    
    <column>
      <img src="/upload/logo.png">
    </column>

  </footers>
</template>


<style scoped>

  .footer {
    display: flex;
    justify-content:  space-between;
    padding: 5vw;
    width: 100%;
    font-size: 0.8rem;
    font-weight: 400;
  }
  
  .einleser .contact {
  color: #333333; }

.nav { display: inline; }
  .links {
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
