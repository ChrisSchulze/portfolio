<template>

  <div class="wrapper">
      <Navbar :logo="$site.themeConfig.logo" />
   <div class="container">
    
    <!-- Works list -->
    
    <transition name="fade" mode="out-in">
        <div v-if="$route.path === '/'">
        <Content/>
      </div>
</transition>
    
    <!-- Single project view -->
    
        <transition name="fade" mode="out-in">
              <div v-if="isSingleProject">
                  <SingleProjectStage  
                  :title="$page.frontmatter.title"
                  :description="$page.frontmatter.description"
                  />
                <Content/>
            <Arrow  
            :project_name="$page.frontmatter.project_name"
            :projecturl="$page.frontmatter.projecturl"
            />
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

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  html {
  
      /* Font */

      font-size: 16px;
      line-height: 21.5px;
      
      /* Colors */
      
      background: #161618;
      color: #818181;
      
      /* Spacing */
      
      
      :root {
  --space-unit:  1em;
  --space-xxxxs: calc(0.125 * var(--space-unit)); 
  --space-xxxs:  calc(0.25 * var(--space-unit));
  --space-xxs:   calc(0.375 * var(--space-unit));
  --space-xs:    calc(0.5 * var(--space-unit));
  --space-sm:    calc(0.75 * var(--space-unit));
  --space-md:    calc(1.25 * var(--space-unit));
  --space-lg:    calc(2 * var(--space-unit));
  --space-xl:    calc(3.25 * var(--space-unit));
  --space-xxl:   calc(5.25 * var(--space-unit));
  --space-xxxl:  calc(8.5 * var(--space-unit));
  --space-xxxxl: calc(13.75 * var(--space-unit));
  --component-padding: var(--space-md);
}
      
  
  @media (max-width: 900px) {
      html { 
        --spacing-xxl: 240px;
        --spacing-xl: 180px;
        --spacing-big: 120px;
        --spacing-medium: 80px;
        --padding-small: 64px;
        --padding-xsmall: 24px;
        --padding-xxsmall: 16px;
        }
  }
  @media (max-width: 400px) {
  
      html {
        --spacing-xxl: 160px;
        --spacing-xl: 120px;
        --spacing-big: 80px;
        --spacing-medium: 64px;
        --padding-small: 24px;
        --padding-xsmall: 24px;
        --padding-xxsmall: 16px;
        }
  }
  
  body {
    font-family: PilatBook, -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Noto Sans", "Ubuntu", "Droid Sans", "Helvetica Neue", sans-serif;  
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  
  .container {
    margin-top: var(--space-xxl);
    }

  img {
    width: 100%;
    max-width: 100%;
    line-height: 0;
    margin: auto auto auto auto;
    padding-bottom: var(--spacing-medium);
  }

  .container {
    padding: 0 5vw;
  }
  
  .project-list {
    margin-top: var(--spacing-big) !important;
    }

  .journal-list, .single-journal {
    width: 800px;
    max-width: 100%;
    margin: 0 auto;
  }
  
  a, a:link, a:visited {
    width: 100%;
    max-width: 870px;
    color: #595959;
    text-decoration: none;
  }

  h1 {
    font-family: "PilatWideDemi";
    width: 100%;
    max-width: 870px;
    font-size: 6vw;
    line-height: 7vw;
    font-weight: 700;
    color: #D1D1D2; 
    margin: 0 auto 0 auto;
    padding-bottom: var(--spacing-medium);
  }
  
  
    @media (min-width: 1440px) {
      h1 { 
          font-size: 100px;
          line-height: 110px;
        }
  }
    @media (max-width: 400px) {
      h1 { 
          font-size: 40px;
          line-height: 44px;
        }
  }
  
  .lead {     max-width: none !important;
              }
  
  .outline {
  letter-spacing: 0.03em;
  color: #161618;

    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #D1D1D2;
}


  h3,h5,h6,p {
    width: 100%;
    max-width: 870px;
  }

    .tight {
  padding-bottom: var(--padding-xsmall);
  }
 
  h2 {
    font-family: "PilatWideDemi";
    width: 100%;
    max-width: 870px;
    font-size: 0.875rem;
    line-height: 1rem;
    letter-spacing: 0.5px;
    color: #D1D1D2;
    padding-bottom: var(--padding-xxsmall);;
    margin: 0 auto 0 auto;
  }

  h3 {
    font-family: "PilatWideDemi" !important;
    font-size: 0.8rem;
    line-height: 0.825rem;
    letter-spacing: 2px;
    color: #D1D1D2;
    margin: auto auto auto auto;
    padding-bottom: var(--padding-xsmall);
  }
  
  h4 {
      font-family: "PilatWideDemi";
      font-size: 0.875rem;
      line-height: 0.875rem;
      letter-spacing: 0.5px;
      width: 100%;
      max-width: 870px;
      margin: 0 auto 3rem auto;
      }

  p {
    font-size: 2rem;
    line-height: 2.6rem;
    letter-spacing: 1.2px;
    margin: auto auto auto auto;
    padding-bottom: var(--spacing-medium);
  }
  
  .bold {
    font-family: "PilatWideDemi" !important;
    color: #D1D1D2 !important;; 
  }
  
  @media (max-width: 900px) {
      p {
          font-size: 1.5em;
          line-height: 1.2em;
        }
  }
  
  @media (max-width: 400px) {
      p { 
          font-size: 1.25em;
          line-height: 1.2em;
        }
  }
  
  .einleser {
  padding-bottom: var(--padding-small);
  }
  

  pre {
    background: var(--color-black);
    padding: 1rem;
    margin: 1rem 0;
  }

  code {
    color: white;
    background: var(--color-black);
    font-size: 0.8rem;
    padding: 0.05rem 0.25rem;
    font-weight: 400;
  }
  
    .post {
    position: relative;
    width: 100%;
    padding-bottom: var(--spacing-big);
    cursor: default;
  }

/*** TRANSITIONS ***/
.fade-enter {
  transform: translateY(40px);
  opacity: 0;
}

.fade-enter-active {
  transition: all 0.6s ease-out;
}

.fade-leave-active {
  transition: all 0.1 ease-out;
}

.fade-leave-to {
  transform: translateY(0px);
  opacity: 0;
}
</style>
