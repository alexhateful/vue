<template>
  <div id="app">
    <div class="d-flex">
      <buttonPlus/>
      <Counter
      :c="counter"
      />
      <buttonMinus/>
    </div>
    <div class="log">{{log}}</div>
  </div>
</template>

<script>
import { eventEmitter } from './main'
// import HelloWorld from './components/HelloWorld'
import ButtonPlus from './components/ButtonPlus'
import ButtonMinus from './components/ButtonMinus'
import Counter from './components/Counter'

export default {
  name: 'App',
  data () {
    return {
      log: '',
      counter: 2
    }
  },
  components: {
    // HelloWorld,
    ButtonPlus,
    ButtonMinus,
    Counter
  },
  created () {
    eventEmitter.$on('counterIncrement', () => { this.log += 'counter incremented\n' })
    eventEmitter.$on('counterDecrement', () => { this.log += 'counter decremented\n' })
  }
}
</script>

<style>
.d-flex {
  display: flex;
}
</style>
