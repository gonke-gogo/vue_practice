<!-- ToDoListApp.vue -->
<template>
  <div>
    <h1>ToDoリスト</h1>
    <task-list :tasks="tasks" @updateTask="updateTask"></task-list>
  </div>
</template>

<script>
import TaskList from "./components/TaskList.vue";

export default {
  components: {
    TaskList
  },
  data() {
    return {
      tasks: [
        { id: 1, text: "牛乳を買う", category: "家事" },
        { id: 2, text: "報告書を書く", category: "仕事" }
      ]
    };
  },
  methods: {
    updateTask(updatedTask) {
      const taskIndex = this.tasks.findIndex(task => task.id === updatedTask.id);
      if (taskIndex !== -1) {
        this.tasks.splice(taskIndex, 1, updatedTask);
      }
    }
  }
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
