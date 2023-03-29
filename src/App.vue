<script>
import AppCounter from './components/AppCounter.vue';
import AppLoader from './components/AppLoader.vue';
import AppMain from './components/AppMain.vue';

import {store} from './store.js'



export default {
  data() {
    return {

      store,
    };
  },
  components: { AppMain, AppCounter, AppLoader }
}
</script>

<template>
  
  <div class="container" >

    <AppLoader v-if="!store.cards.length>0"></AppLoader>

    <AppCounter ></AppCounter>

    <AppMain></AppMain>

  </div>
</template>

<style lang="scss">
.container {
  width: 1000px;
  margin: 20px auto;

 
}
</style>