<template>
  <div id='poop'>
    <button v-on:click="increment">increment 1</button>
    <button v-on:click="decrement">decrement 1</button>
    <p>I'm a Counter! counter is at {{ count }}</p>
  </div>

</template>

<script>
export default {
  props:{
    initialCount: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      count: this.initialCount
    };
  },
  methods: {
    increment: function(event){
      this.count+=1;
    },
    decrement: function(event){
      this.count-=1;
    }
  }
  
};
</script>

<style>
</style>

