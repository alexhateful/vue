<template>
    <button @click="decrement()">-</button>
</template>

<script>
import { eventEmitter } from '../main'
export default {
  name: 'ButtonPlus',
  methods: {
    decrement () {
      eventEmitter.$emit('counterDecrement')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
