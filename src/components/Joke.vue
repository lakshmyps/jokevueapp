<template>
  <div id="app">
    <p class="setup">{{ setup }}<br />
    <p class="text-name">{{ punchline }}</p>
     <p class="button btn"> <button   v-on:click="getnextjoke">Next Joke</button></p>
  </div>  
</template>

<script>
import axios from "axios";

export default {
  name: "Joke",
  data() {
    return {
      punchline: null,
      setup: null,
    };
  },
  created: function () {
    
  },
  methods: {
    getnextjoke: function(){
      //console.log('coming here');
      this.getapicall();
    },
    getapicall: function(){
      axios
      .get("https://official-joke-api.appspot.com/random_joke")
      .then((res) => {
        //this.joke = res.data.setup + res.data.punchline;
        this.setup = res.data.setup;
        this.punchline = res.data.punchline;
      });
    }
  }
};
</script>

