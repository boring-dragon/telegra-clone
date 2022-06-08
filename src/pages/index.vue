<script setup lang="ts">
const state = reactive({
  title: 'MNDF seizes Sri Lankan fishing boat illegally in Maldivian waters',
  author: 'jinas',
})
</script>

<template>
  <div class="container mx-auto max-w-3xl">
    <div class="flex items-start justify-between">
      <div>
        <Textarea v-model="state.title" class="text-4xl" placeholder="Title" />
        <Textarea v-model="state.author" class="text-sm" placeholder="Your name" />
        <Tiptap />
      </div>
      <div>
        <button type="button" class="inline-flex items-center px-4 py-2 border-2 border-gray-900 text-sm font-semibold rounded-full text-gray-900 bg-white focus:outline-none focus:ring-0 uppercase">
          Publish
        </button>
      </div>
    </div>
  </div>
</template>
