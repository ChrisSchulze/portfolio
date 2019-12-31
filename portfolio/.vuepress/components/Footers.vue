<template>
  <footer class="footers" >

    <nav>
      <ul>
        <li>
          <a href="">Link 1</a>
        </li>
      </ul>
    </nav>

    <nav>
      <ul>
        <li>
          <a href="">Link 2</a>
        </li>
      </ul>
    </nav>
    
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

  .li {
    display: inline-block;
    list-style: none;
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
