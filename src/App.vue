<template>
  <h2>{{name}}</h2>
  <div>
    <button v-on:click="name = 'Superman'">Change name</button>
    <button v-on:mouseover="name = 'Superman'">Change name</button>
  </div>

  <h2>{{count}}</h2>
  <div>
    <button v-on:click="count++">Increment</button>
    <button v-on:click="count--">Decrement</button>
  </div>

  <h2>{{count2}}</h2>
  <div>
    <button v-on:click="increment(2)">Increment</button>
    <button v-on:click="decrement">Decrement</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
       name: 'Batman',
       count: 0,
       count2: 0
    }
  },
  methods: {
    increment(num){
      this.count2 += num;
    },
    decrement(){
      this.count2 -= 1;
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
