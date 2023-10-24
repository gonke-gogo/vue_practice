<template>
  <ul>
    <li v-for="task in tasks" :key="task.id">
      {{ task.text }} ({{ task.category }})
      <select @change="changeCategory(task, $event)">
        <option v-for="cat in categories" :key="cat" :value="cat">{{ cat }}</option>
      </select>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["tasks"],
  data() {
    return {
      categories: ["家事", "仕事", "趣味"]
    };
  },
  methods: {
    changeCategory(task, event) {
      const updatedTask = { ...task, category: event.target.value };
      this.$emit("updateTask", updatedTask);
    }
  }
};
</script>
