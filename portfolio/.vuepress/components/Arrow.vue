<template>
<h3>Next Project
		<a class="animated-arrow" :href="projecturl">
               				<span class="the-arrow -left">
                  				<span class="shaft"></span>
                			</span>
                			
				<span class="main">
                 				                  <span class="text">{{ project_name }}</span>
                  			<span class="the-arrow -right">
                    				<span class="shaft"></span>
                  			</span>
				</span>
                	
              </a>
</h3>

</template>

<script>
  export default {
    props: {
    	project_name: {
        type: String,
        required: true
      	},
    	projecturl: {
        type: String,
        required: true
      	}
    }
  }
</script>

<style scoped>

.animated-arrow 	{
	padding-top: var(--padding-xxsmall);
	margin-bottom: var(--spacing-big);
	}

.the-arrow {
	 width: 64px;
	 transition: all 0.2s;
}
 .the-arrow.-left {
	 position: absolute;
	 top: 24px;
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
