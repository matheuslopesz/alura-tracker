<template>
 <main class="columns is-gapless is-multiline">
  <div class="collumn is-one-quarter">

  </div>
  <div class="collumn is-three-quarter">
    <SideBar />
  </div>
 </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';

export default defineComponent({
  name: 'App',
  components: {
    SideBar
  },
  
});
</script>

<style>

</style>
