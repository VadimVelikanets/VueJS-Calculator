<template>
  <div id="app">

    <Calculator :numbs="numbs" :btns="btns"/>
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator
  },
  data: function (){
    return {
      numbs: [1, 2, 3, 4, 5, 6, 7, 8, 9 ,0],
      btns: ['+', '-', '*', '/'],
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
