<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script>
  import Header from '@/components/Header/Header';

  export default {
    name: 'App',
    components: {
      Header
    }
  }
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto:300,400&display=swap');
  @import '@/assets/styles/_variables';

  body {
    background-color: $lightestGray;
    font-family: $font-family;
    margin: 0;
  }
</style>
