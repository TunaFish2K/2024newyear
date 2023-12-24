<script setup lang="ts">
import IndexLantern from './components/IndexLantern.vue'
import IndexWelcome from './components/IndexWindow.vue'
import IndexVase from './components/IndexVase.vue';
import IndexDesk from "./components/IndexDesk.vue";
import IndexFlower from './components/IndexFlower.vue';
</script>

<template>
  <IndexWelcome id="welcome"/>
  <IndexLantern id="lantern_0" class="lantern"/>
  <IndexLantern id="lantern_1" class="lantern"/>
  <IndexLantern id="lantern_2" class="lantern"/>
  <IndexLantern id="lantern_3" class="lantern"/>

  <IndexDesk id="desk" />
  <IndexVase id="vase" />

  <IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower />
  <IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower /><IndexFlower />
</template>

<style scoped>
.lantern {
  transform-origin: center top;
  height: 180px;
  width: auto;
  position: fixed;
  top:-10px;
}
#lantern_0 {
  left:60px; 
}
#lantern_1 {
  left:120px; 
}
#lantern_2 {
  right:120px; 
}
#lantern_3 {
  right:60px; 
}
#welcome {
  position: fixed;
  transform: translate(-50%, -50%);
  left: 50%;
  top: 30%
  
}
#vase {
  position: fixed;
  transform: translate(-50%, -50%);
  left: 50%;
  top: 55%;
}
#desk {
  position: fixed;
  transform: translate( -50%, -50%);
  left: 50%;
  top: 73%;
}
</style>
