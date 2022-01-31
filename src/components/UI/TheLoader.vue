<template>
  <div class="bg-loader">
    <div class="loader">
      <div class="loading-loader">
        <img src="../../assets/loader.png" alt="loader" />
      </div>
      <h3>nOS</h3>
      <h4>by <strong>Juggernaut Studio©</strong></h4>
    </div>
  </div>
</template>

<style scoped>
h3, h4 {
  text-align: center !important;
  font-size: 2rem;
  color: white;
  
}
h4{
    font-size: 1rem !important;
    color: rgb(126, 126, 126);
}
img {
  height: 6rem;
  animation: loading 5s forwards;
  animation: loading 5s;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.bg-loader {
  position: relative;
}
.loader {
  position: absolute;
  display: block;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* @keyframes loading {
        0%{
            transform: rotate(0);
        }
        50%{
            transform: rotate(180);
        }
        100%{
            transform: rotate(359.9999);
        }
    } */

@keyframes loading { 
    from { transform: rotate(0deg); }
    to { transform: rotate(2000deg); } 
} 
</style>
