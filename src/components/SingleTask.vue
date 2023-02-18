<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        {{ taskName }}
      </div>
      <div class="column">
        <StopWatch :timeInSeconds=timeInSeconds />
      </div>
    </div>
  </div>
</template>

<script>  
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";

export default defineComponent({
  name: "SingleTask",
  components: {
    StopWatch,
  },
  props: {
    timeInSeconds: {
      type: Number,
      required: true,
    },
    taskName: {
      type: String,
      required: true,
    },
  }
 
});

</script>

<style scoped>
 .box {
   background-color: #FAF0CA;
 }
</style>