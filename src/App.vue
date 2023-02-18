<template>
 <main class="columns is-gapless is-multiline">
  <div class="column is-one-quarter">
    <SideBar />
  </div>
  <div class="column is-three-quarter">
    <TaskForm @whenSavingTask="saveTask" />

    <div class="task-list">
      <SingleTask 
        v-for="task in tasks"
        :key="task.name" 
        :timeInSeconds="task.timeInSeconds"
        :taskName="task.name" 
      />
    </div>

    <TaskBox  v-if="tasks.length === 0">
      <div class="has-text-centered">
        <p class="is-size-4">No tasks yet</p>
        <p class="is-size-6">Add a task to start tracking time</p>
      </div>
    </TaskBox>
  </div>
 </main>
</template>

<script>
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';
import TaskForm from './components/TaskForm.vue';
import SingleTask from './components/SingleTask.vue';
import TaskBox from './components/TaskBox.vue';

export default defineComponent({
  name: 'App',
  components: {
    SideBar,
    TaskForm,
    SingleTask,
    TaskBox
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
