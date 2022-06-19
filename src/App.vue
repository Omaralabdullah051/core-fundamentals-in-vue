<template>
   <h2 v-if="num === 0">The number is zero</h2>
   <h2 v-else-if="num < 0">The number is negative</h2>
   <h2 v-else-if="num > 0">The number is positive</h2>
   <h2 v-else>Not a number</h2>

  <template v-if="display">
    <h2>Batman</h2>
    <h2>Evolution</h2>
    <h2>Vue</h2>
  </template>

  <h2 v-show="showElement">Using v-show</h2>
  <h2 v-if="showElement">Using v-if</h2>

  <!-- The difference between  v-show and v-if directive is v-show will mount in the DOM and render in the UI even the condition is false. But it toggles the css property display:none to display:block with the specific condition. On the other hand, v-if directive will not mount in the DOM and will not render when the conditionis false. When we need to toggle the display between none to display, v-show is more applicable. Becasue Mount in the DOM again is costly-->
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      num: 5,
      display: true,
      showElement: false
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
