<template>
    <div class="wrapper">  
        <Navbar :logo="$site.themeConfig.logo" />    
    <div class="container">
    
<!-- Works list -->
    
      <transition name="moveInUp">
          <div v-if="$route.path === '/'">
            <Content/>
          </div>
      </transition>
      
<!-- Single project view -->
          
      <transition name="moveInUp">
          <div v-if="isSingleProject">
              <SingleProjectStage  
              :title="$page.frontmatter.title"
              :description="$page.frontmatter.description"
              />
            <Content/>
  <MoreProjects/>
          </div>   
          
      </transition>

        <Footer/>
    </div>
</template>

<script>
  export default {
    computed: {
      isSingleProject() {
        const worksRoute = '/works/'
        const path = this.$route.path
        if (path.includes('works') && path.length >= (worksRoute.length + 1)) {
          return true
        }
      },
      
      
           isSingleJournal() {
        const journalRoute = '/journal/'
        const path = this.$route.path
        if (path.includes('journal') && path.length >= (journalRoute.length + 1)) {
          return true
        }
      }
    },
    updated() {
        // unwrap all images from paragraph tags so we can have
        // different widths inside the content.

        document.querySelectorAll('p img').forEach(image => {
          var wrapper = image.parentNode
          let children = wrapper.children
          let fragment = document.createDocumentFragment()

          Array.from(children).forEach(child => {
            fragment.appendChild(child)
          })

          wrapper.parentNode.replaceChild(fragment, wrapper)

        })
    },
  }
  
</script>

<style>

@font-face {
  font-family: "PilatWideDemi";
  src: local("Pilat Wide Demi"), local("Pilat-Wide-Demi"),
    url("/upload/PilatWide-Demi.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "PilatBook";
  src: local("Pilat Book"), local("Pilat-Book"),
    url("/upload/Pilat-Book.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}
  
  body {
    font-family: "PilatWideDemi", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Noto Sans", "Ubuntu", "Droid Sans", "Helvetica Neue", sans-serif;  
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 16px;
    line-height: 21.5px;
    background: #000000;
    color: #585858;
  }
  
  .container {
    padding: 0 5vw;
    }
    
  .custom {
    margin: 0 auto;
    padding: 0;
    max-width: 1400px;
    }

  :root {
  --space-unit:  1rem;
  --space-xxxxs: calc(0.125 * var(--space-unit)); 
  --space-xxxs:  calc(0.25 * var(--space-unit));
  --space-xxs:   calc(0.375 * var(--space-unit));
  --space-xs:    calc(0.5 * var(--space-unit));
  --space-sm:    calc(0.75 * var(--space-unit));
  --space-md:    calc(1.25 * var(--space-unit));
  --space-lg:    calc(2 * var(--space-unit));
  --space-l:     calc(2.75 * var(--space-unit));
  --space-xl:    calc(3.75 * var(--space-unit));
  --space-xxl:   calc(5 * var(--space-unit));
  --space-xxxl:  calc(8.5 * var(--space-unit));
  --space-xxxxl: calc(10 * var(--space-unit));
  --component-padding: var(--space-md);
  }
  
@media (max-width: 1024px), (min-width: 1024px) {
    :root {
      --space-unit: 2rem;
    }
  }

@media (max-width: 991px) {
    :root {
      --space-unit: 1.75rem;
    }
  } 

@media (max-width: 767px) {
    :root {
      --space-unit: 1.5rem;
    }
  } 

@media (max-width: 575px) {
    :root {
      --space-unit: 1rem;
    }
  } 

@media (max-width: 375px) {
    :root {
      --space-unit: 0.5rem;
    }
  } 

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }


  img {
    width: 100%;
    max-width: 100%;
    line-height: 0;
    border-radius: 2rem;
    margin: auto auto auto auto;
    margin-bottom: var(--space-xxl);
    }
  
  a, a:link, a:visited {
    width: 100%;
    max-width: 870px;
    color: #595959;
    text-decoration: none;
    }

  li {
        font-size: 1rem;
  }

  h1 {
    font-family: "PilatWideDemi";
    width: 100%;
    font-size: var(--space-l);
    line-height: var(--space-l);
    font-weight: 700;
    color: #D1D1D2; 
    margin: 0 auto 0 auto;
    }
  
  .lead { 
    max-width: none !important;
    margin-bottom: var(--space-xxxxl);
    }
  
  .outline {
  letter-spacing: 0.03em;
  color: #000; 
  color: rgba(0, 0, 0, 0);
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #D1D1D2;
  }
  
  .tight {
  padding-top: calc(1.5 * var(--space-xxl));
  padding-left: var(--space-xxl);
  padding-right: var(--space-xxl);
  padding-bottom: var(--space-sm);
  }

  h2 {
    font-family: "PilatWideDemi";
    width: 100%;
    max-width: 870px;
    font-size: 1.6rem;
    line-height: 1rem;
    letter-spacing: 0.5px;
    color: #D1D1D2;
    margin: 0 auto var(--space-lg) auto;
  }
  
  h3,h5,h6,p {
    width: 100%;
    max-width: 870px;
    }

  h3 {
    font-family: "PilatWideDemi" !important;
    font-size: 0.8rem;
    line-height: 0.825rem;
    letter-spacing: 2px;
    color: #D1D1D2;
    margin: auto auto var(--space-md) auto;
  }
  
  h4 {
      font-family: "PilatWideDemi";
      font-size: 0.875rem;
      line-height: 0.875rem;
      letter-spacing: 0.5px;
      width: 100%;
      padding-left: var(--space-xxl);
      margin: var(--space-sm) auto 0 auto;
      }

  p {
    font-size: 2rem;
    line-height: 2.875rem;
    letter-spacing: 1.2px;
    margin: auto auto var(--space-xxl) auto;
  }
  
  .bold {
    font-family: "PilatWideDemi" !important;
    color: #D1D1D2 !important;; 
  }
  
  .einleser {
    margin-bottom: var(--space-xl);
  }
  
  @media (max-width: 900px) {
      p {
          font-size: 1.25em;
          line-height: 1.5em;
        }
  }
  
  @media (max-width: 400px) {
      p { 
          font-size: 1em;
          line-height: 1.5em;
        }
  }
  
    .post {
    position: relative;
    width: 100%;
    margin-bottom: var(--space-lg);
    height: calc(5 * var(--space-xxl));
    border-radius: 2rem;
    box-shadow: inset 0 0 0 1000px rgba(0,0,0,0.5);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }

.moveInUp-enter-active{
  animation: fadeIn 0.6s ease-in-out;
}
@keyframes fadeIn{
  0%{
    opacity: 0;
    transform: translateY(80px);
  }
  100%{
    opacity: 1;
    transform: translateY(0px);
  }
}
</style>
