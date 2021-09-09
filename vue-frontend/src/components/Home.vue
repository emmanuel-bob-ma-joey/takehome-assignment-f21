<template>
  <div>
    <!-- PART 1: Pass in a "complete" prop here -->
    <Instructions v-bind:complete="true"/>
    <!-- PART 4: Modify the Show component to accept all of these props -->
    <p>Add a new show!</p>
    <input v-model="inputName" placeholder="edit me">
    <p>Message is: {{ inputName }}</p>
    <button type="button" v-on:click="submit">submit</button>
    <Show
      
      v-for="show in shows"
      :key="show.id"
      :id="show.id"
      :name="show.name"
      :episodes_seen="show.episodes_seen"
    />
  </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";

export default {
  props:{
    inputName: {
      type: String,
      default: ""
    }
  },
  components: {
    Instructions,
    Show
  },
  data(){
    return {
      shows: [
        { id: 1, name: "Game of Thrones", episodes_seen: 0 },
        { id: 2, name: "Naruto", episodes_seen: 220 },
        { id: 3, name: "Black Mirror", episodes_seen: 3 }
      ]
    };
  },
  methods:{
    submit: function(){
      console.log('poop');
      this.shows.push({id: this.shows.length+1, name: this.inputName, episodes_seen: 0})
      //return {
        // shows: {id: this.shows.length+1, name: inputName, episodes_seen: 0}
      // }
      
    }
  }
};
</script>

<style>
</style>


