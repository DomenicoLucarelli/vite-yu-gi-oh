<script>
import AppCounter from './components/AppCounter.vue';
import AppMain from './components/AppMain.vue';

import {store} from './store.js'



export default {
  data() {
    return {

      store,
    };
  },
  components: { AppMain, AppCounter }
}
</script>

<template>
  
  <div class="container" >

    <AppCounter >

    </AppCounter>
    <AppMain>

    </AppMain>


  </div>
</template>

<style lang="scss">
.container {
  width: 1000px;
  margin: 20px auto;

 
}
</style>