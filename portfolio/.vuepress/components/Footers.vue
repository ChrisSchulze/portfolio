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

  </footer>
</template>


<style scoped>



  .footer {
    display: flex;
    padding: 2rem 0;
    width: 100%;
    margin: 0 auto 0 auto;
    

    bottom: 0;
    left: 0;
    align-items: center;
    justify-content: space-between;
    height: 6rem;

    
    font-size: 0.8rem;
    font-weight: 400;

  }

  .nav li {
    display: inline-block;
    list-style: none;
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
