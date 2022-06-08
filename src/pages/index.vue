<script setup lang="ts">
const state = reactive({
  title: 'MNDF seizes Sri Lankan fishing boat illegally in Maldivian waters',
  author: 'jinas',
  content: {
    type: 'doc',
    content: [
      {
        type: 'paragraph',
        content: [
          {
            type: 'text',
            text: 'Afcons Infrastructure revealed it will be contracting additional batches of engineers to accelerate the construction of Thilamale\' Bridge project.',
          },
        ],
      },
      {
        type: 'paragraph',
        content: [
          {
            type: 'text',
            text: 'The contractor will be hiring extra hands to ensure the project concludes by July 2023, the contracted period of completion.',
          },
        ],
      },
      { type: 'paragraph' },
      {
        type: 'paragraph',
        content: [
          {
            type: 'text',
            text: 'The confirmation was made through a news conference at Afcons Infrastructure\'s headquarters in India in the presence of Maldivian media correspondents.',
          },
        ],
      },
      {
        type: 'paragraph',
        content: [
          {
            type: 'text',
            text: 'During the media trip to India, senior officials of Afcons met with the reporters to provide detailed information about the bridge project.',
          },
        ],
      },
      {
        type: 'heading',
        attrs: { level: 2 },
        content: [{ type: 'text', text: 'The Plan' }],
      },
      { type: 'paragraph' },
    ],
  },
})
</script>

<template>
  <div class="container mx-auto max-w-3xl">
    <div class="flex items-start justify-between">
      <div>
        <Textarea v-model="state.title" class="text-4xl" placeholder="Title" />
        <Textarea v-model="state.author" class="text-sm" placeholder="Your name" />
        <Tiptap v-model="state.content" />
        {{ state.content }}
      </div>
      <div>
        <button class="inline-flex items-center px-4 py-2 border-2 border-gray-900 text-sm font-semibold rounded-full text-gray-900 bg-white focus:outline-none focus:ring-0 uppercase" type="button">
          Publish
        </button>
      </div>
    </div>
  </div>
</template>
