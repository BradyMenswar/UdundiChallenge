<script setup>
import Background from './components/Background.vue'
import Explore from './components/ExplorePopout.vue'
import Socials from './components/Socials.vue'

</script>

<template>
  <main>
    <Background />
    <Explore />
    <Socials />
  </main>
</template>

<style scoped>
  * {
    margin: 0;

    box-sizing: border-box;
    overflow: hidden;
  }
</style>
