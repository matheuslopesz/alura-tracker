<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <StopWatch :timeInSeconds="timeInSeconds" />
    <button class="button" @click="startTimer" :disabled="isStopwatchRunning">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="stopTimer" :disabled="!isStopwatchRunning">
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
      isStopwatchRunning: false,
    };
  },
  methods: {
    startTimer() {
      this.isStopwatchRunning = true;
      this.stopwatch = setInterval(() => {
        this.timeInSeconds++;
      }, 1000);
    },
    stopTimer() {
      this.isStopwatchRunning = false;
      clearInterval(this.stopwatch);
    },
  },
});
</script>
