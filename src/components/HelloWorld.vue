<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div><span>Total: {{ recalculate }}</span></div>
    <div><span>Counter: {{ counter }}</span></div>
    <button id="decButton" @click="decrement()">Decrement</button>
    <button id="incButton" @click="increment()">Increment</button>
    <div>
      Multiplier: <input v-model="multiplier" placeholder="edit me">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data()  {
    return {
      counter: 0,
      multiplier: 5
    }
  },
  methods: {
    increment(){
      this.counter++
    },
    decrement(){
      this.counter--
    }
  },
  computed: {
    recalculate () {
      return ( this.counter * this.multiplier)
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
