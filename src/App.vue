<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
import Home from '@/views/Home.vue'
export default {
  name:'App',
  components:{
    Home
  }

}
</script>
<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  router-link{
    text-decoration: none !important;
  }
  a{
    text-decoration: none !important;
  }

  button:focus{
    box-shadow:none !important;

  }
</style>
