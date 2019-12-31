<template>
  <footer class="footer" >

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
    <p>I'm always happy to meet new people. Give me a call +49 1157 39 240 376, email jan.christian.schulze@gmail.com or visit me. Ⓒ Christian Schulze 2020</p>
    </column>
    
    <column>
    <img href="">
    </column>


  </footer>
</template>


<style scoped>



  .footer {
    display: flex;
    align-items: flex-start;
    padding: 4rem 5vw;
    
    width: 100%;
    margin: 0 auto 0 auto;
    
    align-items: center;
    justify-content: space-between;
    height: 6rem;

    
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
