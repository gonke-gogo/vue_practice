<!-- ToDoListApp.vue -->
<template>
  <div>
    <!-- タスクの入力欄と追加ボタン -->
    <input v-model="newTask" @keyup.enter="addTask"/>
    <button @click="addTask">追加</button>

    <!-- タスクリスト -->
    <ul>
      <li v-for="task in tasks" :key="task.id">
        {{ task.text }}
        <button @click="removeTask(task.id)">削除</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "", // 新しいタスクの入力値
      tasks: [] // タスクリスト
    };
  },
  methods: {
    addTask() {
      // newTaskが空でなければタスクを追加
      if (this.newTask.trim() !== "") {
        this.task.push({ id: Date.now(), text: this.newTask});
        this.newTask = "";
      }
    },
    removeTask(id) {
      // 指定されたIDのタスクを削除
      this.tasks = this.tasks.filter(task => task.id !== id);
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
