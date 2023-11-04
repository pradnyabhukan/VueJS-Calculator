<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
  </div>
</template>

<style scoped>
  .greetings{
    display: flex;
    text-align: center;
    justify-content: center;
  }
  .green{
    color: green;
    font-family: 'Times New Roman', Times, serif;
  }
</style>

