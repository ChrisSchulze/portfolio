<template>
  <div class="wrapper">

    <Navbar :logo="$site.themeConfig.logo" :sticky="$route.path === '/'" />

    <div class="container">

      <!-- Works list -->
      <div
        v-if="$route.path === '/'"
        :style="{
          marginTop: '20vw'
        }"
      >
        <Content/>
      </div>

          <!-- Single project view -->
          <div v-if="isSingleProject"
              :style="{
              marginTop: '20vw'
              }"
          >
      
        <SingleProjectStage  
        :title="$page.frontmatter.title"
        :description="$page.frontmatter.description"
        />
        
        <SingleProjectHeader
          :services="$page.frontmatter.services"
          :year="$page.frontmatter.year.toString()"
          :categories="$page.frontmatter.categories"
        />
        
        <div id="custom"><img :src="$page.frontmatter.thumbnail"></div>
        
        <Content/>

      <!-- Journal list -->
      <div v-if="$route.path === '/journal/'" class="journal-list">
        <Content />
      </div>

      <!-- Single journal -->
      <div v-if="isSingleJournal" class="single-journal">
        <Content/>
      </div>

    </div>

    <Footer />

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
    url("/portfolio/.vuepress/public/upload/PilatWide-Demi.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "PilatBook";
  src: local("Pilat Book"), local("Pilat-Book"),
    url("/portfolio/.vuepress/public/upload/Pilat-Book.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}

  :root {
    --color-black: #1c1c1c;
    --color-highlight: rgba(249, 233, 172, 0.99);
  }

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  *::-moz-selection {
    background: var(--color-highlight);
    color: var(--color-black);
  }

  *::-webkit-selection {
    background: var(--color-highlight);
    color: var(--color-black);
  }

  *::selection {
    background: var(--color-highlight);
    color: var(--color-black);
  }

  html {
  
      /* Font */

      font-size: 16px;
      line-height: 21.5px;
      
      /* Colors */
      
      background: #1D1D1F;
      color: #595959;
      
      /* Padding */
      
      --padding-big: 160px;
      --padding-medium: 120px;
      --padding-small: 80px;
      --padding-xsmall: 40px;
  }
  
  @media (max-width: 900px) {
      html { 
        --padding-big: 120px;
        --padding-medium: 80px;
        --padding-small: 40px;
        --padding-xsmall: 40px;
        }
  }
  @media (max-width: 400px) {
  
      html { 
        --padding-big: 64px;
        --padding-medium: 40px;
        --padding-small: 24px;
        --padding-xsmall: 24px;
        }
  }
  
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Noto Sans", "Ubuntu", "Droid Sans", "Helvetica Neue", sans-serif;  
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  img {
    width: 100%;
    max-width: 100%;
    line-height: 0;
    margin: auto auto auto auto;
    padding-bottom: var(--padding-big);
  }

  .container {
    padding: 0 5vw;
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

  h3,h5,h6,p {
    width: 100%;
    max-width: 600px;
  }

  h1 {
    font-family: "PilatWideDemi";
    width: 100%;
    max-width: 870px;
    font-size: 6.854em;
    line-height: 1em;
    font-weight: 700;
    color: #D1D1D2; 
    margin: 0 auto 0 auto;
    padding-bottom: var(--padding-big);
  }
  
    @media (max-width: 900px) {
      h1 {
          font-size: 4.236em;
          line-height: 1em;
        }
  }
  
    @media (max-width: 400px) {
      h1 { 
          font-size: 2.618em;
          line-height: 1em;
        }
  }
  
  .outline {
  color: transparent;
  text-stroke: 0.5px rgba(210,210,210, 1);
  -webkit-text-stroke: 0.5px rgba(210,210,210, 1); 
  }
  
 
  h2 {
    width: 100%;
    max-width: 870px;
    font-size: 0.6rem;
    line-height: 0.75rem;
    letter-spacing: 0.75px;
    font-weight: 700;
    color: #333333;
    margin: auto auto 0.25rem auto;
  }

  h3 {
    font-size: 0.6rem;
    line-height: 0.75rem;
    letter-spacing: 0.75px;
    font-weight: 700;
    color: #333333;
    margin: auto auto 0.25rem auto;
  }
  
  h4 {
      width: 100%;
      max-width: 870px;
      margin: 0 auto 3rem auto;
      }

  p {
    font-size: 1.5em;
    line-height: 1.5em;
    letter-spacing: 1.25px;
    margin: auto auto auto auto;
    padding-bottom: var(--padding-big);
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
  
  .einleser {
  padding-bottom: var(--padding-xsmall);
  }
  
  .label {
    font-size: 0.6rem;
    line-height: 0.75rem;
    letter-spacing: 0.75px;
    font-weight: 700;
    color: #333333;
    margin: auto auto 0.25rem auto;
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
    padding-bottom: var(--padding-big);
    cursor: default;
  }

</style>
