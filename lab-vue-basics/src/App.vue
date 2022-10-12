<template>
  <NavBar />
  <div class="comp-vs-opt">
    <div><IterationsCompositionStyle /></div>
    <div> <IterationsOptionsStyle /></div>
   
  </div>

  <Footer />
</template>
<script setup>
import NavBar from './components/NavBar.vue';
import Footer from './components/Footer.vue';
import IterationsCompositionStyle from './components/IterationsCompositionStyle.vue';
import IterationsOptionsStyle from './components/IterationsOptionsStyle.vue';
</script>
<style scoped>
.comp-vs-opt {
  display: flex;
  justify-content: space-around;
}
</style>