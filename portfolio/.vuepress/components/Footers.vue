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
