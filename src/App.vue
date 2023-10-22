<!-- CounterApp.vue -->
<template>
  <div>
    <!-- 現在のカウントを表示 -->
    <p>Current Count: {{ currentCount }}</p>
    <!-- インクリメントとデクリメントのボタン -->
    <button @click="increment">+1</button>
    <button @click="decrement">-1</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentCount: 0 // 初期値は0
    };
  },
  methods: {
    // TODO: インクリメントとデクリメントのメソッドを実装
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
