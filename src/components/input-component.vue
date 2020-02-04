<template>
      <div class="columns">
        <div class="column">
           <input 
           v-model="msg" 
           :placeholder="placedata" 
           v-on:keyup.enter="monitorEnterKey"
           class="input is-small" type="text"/>
        </div>
      </div>
</template>

<script>
export default {
    name:'inputComponent',
    props:['placedata'],
    data(){
      return{
        msg: ''
      }
    },
    methods:{
      monitorEnterKey(){
        this.$emit('newInput', {
          note: this.msg,
          timestamp: new Date().toLocaleString()
        });
      }
    }
}
</script>

<style lang="scss">
.container{
    max-width: 500px
}
</style>