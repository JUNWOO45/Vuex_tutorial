<template>
  <div id="app">
    <div id="app">
      Parent counter : {{ parentCounter }} <br>
      <button @click="addCounter">+</button>
      <button @click="subCounter">-</button>
      <child></child>
    </div>
  </div>
</template>

<script>
  import Child from './Child.vue';
  import { mapGetters } from 'vuex';

  export default {
    methods: {
      // addCounter() {
      //   this.$store.commit('addCounter');
      // },
      addCounter() {
        this.$store.dispatch('addCounter')
      },
      subCounter() {
        this.$store.state.counter--;
      }
    },
    components: {
      'child': Child
    },
    computed: mapGetters({
      parentCounter: 'getCounter'
    })
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
