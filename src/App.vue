<template>
  <h2>Fullname- {{firstName}} {{lastName}}</h2>
  <h2>Computed fullname- {{fullName}}</h2>
  <button @click="changeFullName">Change fullname</button>

  <h2>Total - {{items.reduce((total, curr) => (total = total + curr.price),0)}}</h2>
  <h2>Computed Total - {{total}}</h2>
  <h2>Method Total - {{getTotal()}}</h2>
  <input type="text" v-model="country">

  <template v-for="item in items" :key="item.id">
     <h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
  </template>

  <h2 v-for="item in expensiveItems" :key="item.id">
    {{item.title}} {{item.price}}
  </h2>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      firstName: 'Bruce',
      lastName: 'Wayne',
      items: [
        {
          id: 1,
          title: 'TV',
          price: 100
        },
        {
          id: 2,
          title: 'Phone',
          price: 200
        },
        {
          id: 3,
          title: 'Laptop',
          price: 300
        },
      ],
      country: "BD"
    }
  },
  methods: {
    getTotal(){
        console.log('getTotal Method');
          return this.items.reduce((total, curr) => (total = total + curr.price),0);      
    },
    changeFullName(){
      this.fullName = 'Clark kent'
    }
  },
  computed: {
    fullName: {
      get(){
        return `${this.firstName} ${this.lastName}`
      },
      set(value){
         const names = value.split(' ');
         this.firstName = names[0];
         this.lastName = names[1];
      }
    },
    total(){
      console.log('Total computed');
      return this.items.reduce((total, curr) => (total = total + curr.price),0);
    },
    expensiveItems(){
      return this.items.filter(item => item.price > 100);
    }
  }
  // Computed properties VS methods
  // Computed properties are highly performant as they are cached calculations which only update when their dependencies change. On the other hand, methods are always recalculated when the corrosping HTML is rendered.
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
