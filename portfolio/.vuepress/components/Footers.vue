<template>
  <footer class="footers" >
  
  <column>
      <ul class="links">
        <li>
          <a href="">Work</a>
        </li>
        <li>
          <a href="">Contact</a>
        </li>
        </ul>
    </column>
    
    <column>
    <p class="einleser">I'm always happy to meet new people. Give me a call +49 1157 39 240 376 or send me an email.</p>
    </column>
    
    <column>
    <img src="/upload/logo.png">
    </column>


  </footers>
</template>


<style scoped>



  .footers {
    display: flex;
    justify-content:  space-between;
    
    padding: 5vw;
    width: 100%;
    
    font-size: 0.8rem;
    font-weight: 400;

  }

  .links {
    display: inline-block;
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
