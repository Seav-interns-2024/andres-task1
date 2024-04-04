<template>
    <div v-if="showGif" class="gif-showcase">
      <!-- Your GIF here -->
      <img src="@/assets/gif.gif" alt="GIF Showcase" class="gif-image">
    </div>
  </template>
  
  <script>
  export default {
    name: 'Home',
    data() {
      return {
        showGif: true
      };
    },
    mounted() {
      setTimeout(() => {
        this.showGif = false;
      }, 3000);
    }
  };
  </script>
  
  <style scoped>
  .gif-showcase {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 9999;
  }
  
  .gif-image {
    width: 1600px;
    height: 1000px;
  }
  </style>
  