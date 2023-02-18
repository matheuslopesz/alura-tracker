<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Form for task creation">
        <input 
          type="text"
          class="input"
          placeholder="Add task"
          v-model="taskName" 
        />
      </div>
      <div class="column">
       <TimerTask @whenTimerStops="finishTask"/>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import TimerTask from "./TimerTask.vue";

export default defineComponent({
  name: "TaskForm",
  emits: ['whenSavingTask'],
  components: {
    TimerTask,
  },
  data() {
    return {
      taskName: '',
    };
  },
  methods: {
    finishTask(timeInSeconds) {
      this.$emit('whenSavingTask', {
        name: this.taskName,
        timeInSeconds,
      });
      this.description = '';
    },
  },
});
</script>
