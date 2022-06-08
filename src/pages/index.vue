<script setup lang="ts">
const state = reactive({
  title: 'sdfdsf',
  author: 'jinas',
})
</script>

<template>
  <div class="container mx-auto max-w-3xl">
    <Textarea v-model="state.title" placeholder="Title" />
  </div>
</template>
