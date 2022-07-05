<template>
 <h3>Hello World {{name}}</h3>
   <h4>{{counter}}</h4>
   <h4>{{doubleCount}}</h4>
  <button @click="add(15)">Click Me</button>
  <button @click="clear">Reset Store</button>
</template>

<script setup>
import { useCounterStore } from '@/store/useCounter';
import {  storeToRefs } from 'pinia';

    const main = useCounterStore();
    const {counter,name,doubleCount} =storeToRefs(main);
    
    //  const {addOne} = main;
    // const {addOne} = mapActions(useCounterStore,["addOne"]);

    function add(value){
      //  main.$patch({
      //   counter:counter.value + value
      //  });
      main.$patch(state => (state.counter+=value));
    }
    // function reset(){
    //   main.$reset();
    // }
    function clear(){
      main.$state={counter:123,name:'bob'};
    }
  main.$subscribe((mutation,state) =>{
    console.log("mutation",mutation);
    console.log("state",state);

  });
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
