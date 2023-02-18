<template>
  <section class="is-flex is-align-items-center is-justify-content-space-between">
    <StopWatch :timeInSeconds="timeInSeconds" />
    <TaskButton
      :disabled="isStopwatchRunning"
      icon="fas fa-play"
      text="Start"
      @clicked="startTimer"
    />
    <TaskButton
      :disabled="!isStopwatchRunning"
      icon="fas fa-play"
      text="Stop"
      @clicked="stopTimer"
    />
  </section>
</template>

<script>
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";
import TaskButton from "./TaskButton.vue";

export default defineComponent({
  name: "TimerTask",
  emits: ["whenTimerStops"],
  components: {
    StopWatch,
    TaskButton
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
      this.$emit('whenTimerStops', this.timeInSeconds);
      this.timeInSeconds = 0;
    },
  },
});
</script>
