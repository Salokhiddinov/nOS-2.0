<template>
<div class="base-bg">
   <BaseBackground class="base-background">
      <TheLoader class="the-loader" v-if="loader"/>
      <TheLockscreen class="the-lockscreen" />
      <BaseGrid class="base-grid" />
      <TheStart class="the-start" />
      <BaseWindow class="base-window">
      </BaseWindow>
   </BaseBackground>
   
</div>
</template>

<script>
import BaseBackground from "./components/base-components/BaseBackground.vue"
import BaseGrid from './components/UI/BaseGrid.vue'
import TheLockscreen from './components/UI/TheLockscreen.vue'
import TheStart from './components/UI/TheStart.vue'
import TheLoader from './components/UI/TheLoader.vue'

export default {
   components:{BaseBackground, BaseGrid, TheStart, TheLockscreen, TheLoader},
   data(){
      return{
         loader: true,
         isLocked: true,
      }
   },
   mounted(){
      setInterval(() => {
         this.loader = false;
      }, 5000);
   },
   methods:{
      disableLock(isLocked){
         this.isLocked = isLocked;
      }
   }
}


</script>

<style>
.base-bg{
   margin: 0;
   padding: 0;
   box-sizing: border-box;
   position: relative;
   /* overflow: hidden; */
   font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.base-background{
   position: relative;
   width: 100%;
   max-height: 100vh;
   size: cover;
   z-index: -1;
   margin: 0;
   padding: 0;
   background-position: center;
   
   
}
.the-loader{
   position: absolute;
   display: block;
   z-index: 10;
   background-color: rgba(0, 0, 0, 0.952);
   width: 100%;
   height: 100vh;
}
.base-grid{
   position: absolute;
   margin: 0;
   padding: 0;
   z-index: 2;
   top: 15px;
   left: 15px;
   animation-name: moveInLeft;
   animation-duration: 0.5s;
   animation-timing-function: ease-out;
}
.base-window{
   position: absolute;
   display: block;
   z-index: 4;
}

.the-start{
   display: block;
   position: absolute;
   z-index: 3;
   right: 20px;
   top: 20px;
  
   
}
.base-blur{
   filter: blur(1px);
   position: absolute;
   display: block;
   z-index: 4;
}
.the-lockscreen{
   display: block;
   position: absolute;
   z-index: 5;
}

.the-lockscreen:after{
   animation-name: lockHide;
   animation-duration: 2s;
   animation-timing-function: ease-out;
}

@keyframes moveInLeft{
   0%{
      transform: translateX(-50px);
      opacity: 0;
   }
   100%{
      transform: translateX(0);
      opacity: 1;
   }
}
@keyframes moveInLeft1{
   0%{
      transform: translateX(-20px);
      opacity: 0;
   }
   100%{
      transform: translateX(0);
      opacity: 1;
   }
}
@keyframes moveInRight{
   0%{
      transform: translateX(50px);
      opacity: 0;
   }
   100%{
      transform: translateX(0);
      opacity: 1;
   }
}

@keyframes lockHide {
   0%{
      transform: translateX(0);
      opacity: 1;
   }
   100%{
      transform: translateY(-200px);
      opacity: 0;
   }
}

@keyframes lockShow {
   0%{
      opacity: 0;
   }
   100%{
      opacity: 1;
   }
}
</style>