<template>
  <div class="counter">{{c}}</div>
</template>

<script>
import { eventEmitter } from '../main'
export default {
  props: ['c'],
  name: 'Counter',
  data () {
    return {
      // c: 0
    }
  },
  created () {
    eventEmitter.$on('counterIncrement', () => { this.c++ })
    eventEmitter.$on('counterDecrement', () => {
      if (this.c - 1 >= 0) {
        this.c--
      }
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .counter {
    border: 1px solid black;
    margin: - 10px;
    padding: 5px;
  }
</style>
