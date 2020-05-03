<template>
  <footer class="footer" >  

      <column class="text">
        <h1 class="lead">Let’s create something valuable together.</h1>
      </column>
      <column class="logo">
        <img class="small" src="/upload/logo.png">
      </column>

	<h4>
		<a class="animated-arrow" href="www.google.de">
		
                <span class="the-arrow -left">
                  <span class="shaft"></span>
                </span>
                <span class="main">
                  <span class="text">
                    Explore Project
                  </span>
                  <span class="the-arrow -right">
                    <span class="shaft"></span>
                  </span>
                </span>
		</a>
              </h4>

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

.the-arrow {
	 width: 64px;
	 transition: all 0.2s;
}
 .the-arrow.-left {
	 position: absolute;
	 top: 60%;
	 left: 0rem;
}
 .the-arrow.-left > .shaft {
	 width: 0;
	 background-color: #999;
}
 .the-arrow.-left > .shaft:before, .the-arrow.-left > .shaft:after {
	 width: 0;
	 background-color: #999;
}
 .the-arrow.-left > .shaft:before {
	 transform: rotate(0);
}
 .the-arrow.-left > .shaft:after {
	 transform: rotate(0);
}
 .the-arrow.-right {
	 top: 3px;
}
 .the-arrow.-right > .shaft {
	 width: 64px;
	 transition-delay: 0.2s;
}
 .the-arrow.-right > .shaft:before, .the-arrow.-right > .shaft:after {
	 width: 8px;
	 transition-delay: 0.3s;
	 transition: all 0.5s;
}
 .the-arrow.-right > .shaft:before {
	 transform: rotate(40deg);
}
 .the-arrow.-right > .shaft:after {
	 transform: rotate(-40deg);
}
 .the-arrow > .shaft {
	 background-color: #999;
	 display: block;
	 height: 1px;
	 position: relative;
	 transition: all 0.2s;
	 transition-delay: 0;
	 will-change: transform;
}
 .the-arrow > .shaft:before, .the-arrow > .shaft:after {
	 background-color: #999;
	 content: '';
	 display: block;
	 height: 1px;
	 position: absolute;
	 top: 0;
	 right: 0;
	 transition: all 0.2s;
	 transition-delay: 0;
}
 .the-arrow > .shaft:before {
	 transform-origin: top right;
}
 .the-arrow > .shaft:after {
	 transform-origin: bottom right;
}
 .animated-arrow {
	 display: inline-block;
	 color: #999;
	 font-size: 1em !important;
	 text-decoration: none;
	 position: relative;
	 transition: all 0.2s;
}
 .animated-arrow:hover {
	 color: #eaeaea;
}
 .animated-arrow:hover > .the-arrow.-left > .shaft {
	 width: 64px;
	 transition-delay: 0.1s;
	 background-color: #eaeaea;
}
 .animated-arrow:hover > .the-arrow.-left > .shaft:before, .animated-arrow:hover > .the-arrow.-left > .shaft:after {
	 width: 8px;
	 transition-delay: 0.1s;
	 background-color: #eaeaea;
}
 .animated-arrow:hover > .the-arrow.-left > .shaft:before {
	 transform: rotate(40deg);
}
 .animated-arrow:hover > .the-arrow.-left > .shaft:after {
	 transform: rotate(-40deg);
}
 .animated-arrow:hover > .main {
	 transform: translateX(80px);
}
 .animated-arrow:hover > .main > .the-arrow.-right > .shaft {
	 width: 0;
	 transform: translateX(200%);
	 transition-delay: 0;
}
 .animated-arrow:hover > .main > .the-arrow.-right > .shaft:before, .animated-arrow:hover > .main > .the-arrow.-right > .shaft:after {
	 width: 0;
	 transition-delay: 0;
	 transition: all 0.1s;
}
 .animated-arrow:hover > .main > .the-arrow.-right > .shaft:before {
	 transform: rotate(0);
}
 .animated-arrow:hover > .main > .the-arrow.-right > .shaft:after {
	 transform: rotate(0);
}
 .animated-arrow > .main {
	 display: flex;
	 align-items: center;
	 transition: all 0.2s;
}
 .animated-arrow > .main > .text {
	 margin: 0 16px 0 0;
	 line-height: 1;
}
 .animated-arrow > .main > .the-arrow {
	 position: relative;
}
    
</style>
