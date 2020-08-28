<template>
  <div id="app">

    <MyJumbotron v-bind:list="list" @toggle="emitToggleEvent" @inputSend="inputEmitEvent"/>  
    
  </div>

  
</template>

<script>
import MyJumbotron from './components/MyJumbotron.vue'


import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  name: 'App',
  components: {
    MyJumbotron,
  },
  
  data: function() {
    return {
      list: [
       {id: 0, name: "Ecrire le sujet", todo: true},
       {id: 1, name: "Faire le sujet", todo: true},
       {id: 2, name: "Vendre le sujet", todo: true},
       {id: 3, name: "Partir en vaccances", todo: true},
       ],
    }
  },

  methods: {
    emitToggleEvent(id){
      this.list[id.list].todo = !this.list[id.list].todo
      },
     inputEmitEvent(my_input){
      let newTodo= {id:this.list.length, name: my_input, todo: true};
      this.list.push(newTodo);
      console.log(newTodo)
        }

   
  }
}
</script>

<style>

</style>
