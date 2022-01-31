<template >
<div id="background">
  <v-vanta class="vanta" effect="waves" :options="options"></v-vanta>
  <slot></slot>
</div>
</template>

<script>
import VVanta from 'vue-vanta';

export default {
  components: { VVanta },
  data() {
    return {
      options: {
        mouseControls: true,
        touchControls: true,
        gyroControls: false,
        minWidth: 200.0,
        minHeight: 746.0,
        scale: 1.0,
        scaleMobile: 1.0,
        color: 0x90a0c,
      },
    };
  },
};


</script>
