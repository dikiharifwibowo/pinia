<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import CardCounter from './components/CardCounter.vue'
import ButtonCounter from './components/ButtonCounter.vue'
</script>

<template>
  <div class="container mx-auto px-4">
    <div class="flex flex-col items-center gap-8">
      <CardCounter/>
      <ButtonCounter/>
    </div>
  </div>
</template>

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
