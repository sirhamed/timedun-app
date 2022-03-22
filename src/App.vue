<script>
import LoadTime from './components/LoadTime.vue'
export default {
  components : {
    LoadTime,
  }
}
</script>

<template>
  <div class="BG-Page">
      <load-time></load-time>
  </div>
</template>

<style>
  *{
    padding: 0;
    margin: 0;
  }

  .BG-Page{
    height: 100vh;

    background-color: rgb(219, 229, 231);
    background-image: url('./assets/bg2.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  
    display: flex;
    align-items: center;
  }
</style>