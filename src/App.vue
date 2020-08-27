<template>
  <div id="app">
    <Navbar></Navbar>
    <router-view/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';

export default {
  components: {
    Navbar
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC&display=swap');

body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Noto Sans TC', sans-serif;
  background-color: $secondary-color;
}

</style>
