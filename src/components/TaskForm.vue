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
          <section>
            <strong>{{ spentTime }}</strong>
          </section>
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

export default defineComponent({
  name: "TaskForm",
  data() {
    return {
      timeInSeconds: 0
    }
  },
  computed: {
    spentTime() {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8);
    }
  },
  methods: {
    startTimer() {
      setInterval(() => {
        this.timeInSeconds++;
      }, 1000);
    },
    stopTimer() {
      console.log("stop timer");
    },
  },
});
</script>
