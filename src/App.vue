<template>
  <HelloWorld msg="Hello" />
  <!-- <ComputedVariable :start="30" v-for="(item, index) in 300" :key="index" /> -->
  <ComponentSplit />
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ComputedVariable from './components/ComputedVariable.vue'
import ComponentSplit from './components/ComponentSplit/index.vue'
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