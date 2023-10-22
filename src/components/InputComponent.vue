<template>
  <input v-model="localMessage" @input="updateMessage">
</template>

<script>
export default {
  props: ['message'],
  data() {
    return {
      localMessage: this.message
    };
  },
  methods: {
    updateMessage() {
      this.$emit('update:message', this.localMessage);
    }
  }
}
</script>
