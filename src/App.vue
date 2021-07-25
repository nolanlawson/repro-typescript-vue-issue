<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  <div ref="root"></div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import { Picker } from 'emoji-picker-element'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    const root = this.$refs.root as HTMLDivElement
    root.appendChild(new Picker()) // I also get type error here as it is expecting of type DOM
  },
})
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
