<template>
  <div class="base-start">
    <a href="">
        <img src="../../assets/logoff.png" alt="log off" v-show="logOffIsVisible" class="log-off">
    </a>
    <img src="../../assets/hide.png" alt="hide" v-show="logOffIsVisible" @click="toggleLogoffVisibility">
    <img src="../../assets/start.png" alt="start" v-show="!logOffIsVisible" @click="toggleLogoffVisibility" class="start">
  </div>
</template>

<script>
export default {
    data(){
        return{
            logOffIsVisible: false
        }
    },
    methods:{
        toggleLogoffVisibility(){
            this.logOffIsVisible = !this.logOffIsVisible
        }
    }
}
</script>

<style scoped>
div {
  background-color: rgba(119, 119, 119, 0.24);
  border-radius: 200px;
  
}
img{
    height: 25px;
    padding: 15px 20px;
    transition: all 0.2s;
}
img:hover{
    transform: scale(1.3);
    
}
img:active{
    transform: translateY(2px);
    
}
img::after{
    animation-name: moveInRight;
    animation-duration: 0.5s;
    animation-timing-function: ease-out;
}
.log-off{
    animation-name: moveInRight;
    animation-duration: 0.5s;
    animation-timing-function: ease-out;
}
.start{
    animation-name: moveInLeft1;
    animation-duration: 0.4s;
    animation-timing-function: ease-out;
}
</style>
