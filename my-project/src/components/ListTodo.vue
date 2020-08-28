<template>
 
<div id="listTodo">
 
<ul >
  <SingleTodo v-for="item in list" :key="item.id" v-bind:todo="item" @toggle="emitToggleEvent"></SingleTodo>

</ul>
 
</div>

</template>

<script>

import SingleTodo from './SingleTodo.vue'

export default {
  name: 'ListTodo',
   components: {
    SingleTodo,
  },
 props: ['list'],
  methods: {
  emitToggleEvent(id){

  this.$emit('toggle', id)}
  }
  }
  
  

</script>
<style>


li {
list-style: none;
}

</style>