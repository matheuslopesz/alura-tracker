<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Form for task creation">
        <input type="text" class="input" placeholder="Add task" />
      </div>
      <div class="column">
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
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
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";

export default defineComponent({
  name: "TaskForm",
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
