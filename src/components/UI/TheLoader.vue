<template>
  <div class="bg-loader">
    <div class="loader">
      <h3>Loading</h3>
      <div class="loading-loader">
        <img src="../../assets/loader.png" alt="loader" />
      </div>
    </div>
  </div>
</template>

<style scoped>
h3 {
  text-align: center;
  font-size: 2rem;
  color: white;
}
img {
  height: 10rem;
  animation: loading 5s forwards;
  margin: auto;
  animation: loading 8s;
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
    to { transform: rotate(9000deg); } 
} 
</style>
