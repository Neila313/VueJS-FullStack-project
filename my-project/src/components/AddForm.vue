<template>
 
<div class="mx-auto" style="width: 400px;">
  <b-form inline class="text-center">
 

    <label class="sr-only" for="inline-form-input-username">Username</label>
    <b-input-group prepend="NewTask" class="mb-2 mr-sm-2 mb-sm-0">

      <b-input v-model="my_input" id="inline-form-input-username" type="text" placeholder="Todo name"></b-input>
    </b-input-group>

 <b-button squared variant="outline-secondary" @click="inputEmitEvent"> <b-icon icon="file-plus"></b-icon> Add </b-button>  
 </b-form>
</div>


</template>

<script>

export default {
    name: 'AddForm',
      data() {
       return {
        my_input: ""
       }
     
    } , 

    methods: {
        inputEmitEvent(){
            this.$emit('inputSend', this.my_input);
            this.my_input= "";
        }
    }

  
  }

</script>
<style>

</style>
