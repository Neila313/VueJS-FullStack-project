<template>
 
<div id="jumbotron">
    
  <b-jumbotron class="text-center">
    <template v-slot:header>Todo List</template>

    <template v-slot:lead>
    New Features we will have to done for this project
    </template>

    <hr class="my-4">
    <p>
     Easy to use, we created this web app just for you ! 
    </p>

    <ListTodo v-bind:list="list" @toggle="emitToggleEvent" ></ListTodo>
    <AddForm @inputSend="inputEmitEvent"></AddForm>

  </b-jumbotron>
</div>

</template>

<script>
import ListTodo from './ListTodo.vue'
import AddForm from './AddForm.vue'

export default {
  name: 'MyJumbotron',
  components: {
    ListTodo,
    AddForm,
  },
 props:  ['list'],
 methods: {
   emitToggleEvent(id){
     this.$emit('toggle', id)
   },
   inputEmitEvent(my_input){
      this.$emit('inputSend', my_input);
        }
  
 }
  
  }

</script>
<style>


li {
list-style: none;
}

</style>
