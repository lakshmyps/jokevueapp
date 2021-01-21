<template>
  <div id="app">
  <p class="joke"> <Joke /></p>
  </div>
</template>

<script>
import Joke from './components/Joke.vue'

export default {
  name: 'app',
  components: {
    Joke
  }
}
</script>

 