<template>
  <h3>Hello World</h3>
  <h4>{{counter}}</h4>
</template>

<script setup lang="ts">
 import { useCounterStore } from '../store/useCounter';
 const main = useCounterStore();
 const {counter} =main;
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
