<template>
  <h2>{{name}}</h2>
  <div>
    <!-- By default Vue give us the access of event in methods. But we can pass it also manually -->
    <button @click="changeName($event), increment(1, $event)">Change name</button>
  </div>

  <h2>{{count}}</h2>
  <div>
    <button @click="count++">Increment</button>
    <button @click="count--">Decrement</button>
  </div>

  <h2>{{count2}}</h2>
  <div>
    <button @click="increment(2, $event)">Increment</button>
    <button @click="decrement">Decrement</button>
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
    changeName(event){
      this.name="Superman"
      console.log(event);
    },
    increment(num,event){
      this.count2 += num;
      console.log(event);
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
