<template>
 
<li  v-if="todo.todo == true" @click="emitCustomEvent">   <b-icon icon="check2-circle"></b-icon>{{todo.name}}</li>
<li class="line" v-else @click="emitCustomEvent">   <b-icon icon="check-circle-fill"></b-icon>{{todo.name}}</li>


</template>

<script>

export default {
  name: 'SingleTodo',  
  props: ['todo'],

  methods: {
  emitCustomEvent(){

  this.$emit('toggle' , {list: this.todo.id})
  
  }
  }
  }

</script>
<style>
.line {
  text-decoration-line: line-through;
  text-decoration-color: black;
  color: grey
}

.line:hover{
  color: grey
  
}
.line:active{
  color: grey
  
}
</style>
