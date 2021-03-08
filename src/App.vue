<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1> {{ count }} </h1>
  <HelloWorld
    @count-add="payload => count += payload.number"
    @count-remove="count --"
    msg="Hello Vue 3.0 + Vite"/>
</template>

<script>
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const count = ref(0)
    return { count }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>