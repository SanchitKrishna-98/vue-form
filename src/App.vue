<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/payoda.png">
    <Test/>
  </div>
</template>

<script>
import Test from './components/Test.vue'
export default {
  name: 'app',
  components: {
    Test
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #fcfcfc;
  margin-top: 80px;
  background-color: rgba(35, 120, 126, 0.5);
}
</style>
