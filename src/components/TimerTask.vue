<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <StopWatch :timeInSeconds="timeInSeconds" />
    <button class="button" @click="startTimer">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="stopTimer">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";

export default defineComponent({
  name: "TimerTask",
  components: {
    StopWatch,
  },
  data() {
    return {
      timeInSeconds: 0,
      stopwatch: 0,
    };
  },
  methods: {
    startTimer() {
      this.stopwatch = setInterval(() => {
        this.timeInSeconds++;
      }, 1000);
    },
    stopTimer() {
      clearInterval(this.stopwatch);
    },
  },
});
</script>
