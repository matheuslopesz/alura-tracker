<template>
 <main class="columns is-gapless is-multiline">
  <div class="column is-one-quarter">
    <SideBar />
  </div>
  <div class="column is-three-quarter">
    <TaskForm @whenSavingTask="saveTask" />

    <div class="task-list">
      <SingleTask v-for="task in tasks" :key="task.name" :timeInSeconds="task.timeInSeconds" :taskName="task.name" />
    </div>
  </div>
 </main>
</template>

<script>
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';
import TaskForm from './components/TaskForm.vue';
import SingleTask from './components/SingleTask.vue';

export default defineComponent({
  name: 'App',
  components: {
    SideBar,
    TaskForm,
    SingleTask
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    saveTask(task) {
      this.tasks.push(task);
    },
  },
  
  
});
</script>

<style>
.task-list {
  padding: 1.25rem;
}
</style>
