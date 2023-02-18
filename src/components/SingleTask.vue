<template>
  <TaskBox>
    <div class="columns">
      <div class="column is-7">
        {{ taskName || 'No task name'}}
      </div>
      <div class="column">
        <StopWatch :timeInSeconds=timeInSeconds />
      </div>
    </div>
  </TaskBox>
</template>

<script>  
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";
import TaskBox from "./TaskBox.vue";

export default defineComponent({
  name: "SingleTask",
  components: {
    StopWatch,
    TaskBox,
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