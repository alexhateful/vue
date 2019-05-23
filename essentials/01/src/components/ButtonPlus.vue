<template>
    <button @click="increment()">+</button>
</template>

<script>
import { eventEmitter } from '../main'
export default {
  props: ['c'],
  name: 'ButtonPlus',
  methods: {
    increment () {
      eventEmitter.$emit('counterIncrement')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
