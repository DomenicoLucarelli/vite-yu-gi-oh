<script>
import AppMain from './components/AppMain.vue';

export default {
  data() {
    return {};
  },
  components: { AppMain, }
}
</script>

<template>
  <div class="container">

    <AppMain></AppMain>

  </div>
</template>

<style lang="scss">
.container {
  width: 1000px;
  margin: 20px auto;
}
</style>