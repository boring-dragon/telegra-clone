<script setup lang="ts">
import { EditorContent, useEditor } from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'
import Placeholder from '@tiptap/extension-placeholder'

const props = defineProps({
  modelValue: {
    required: true,
  },
})

const emit = defineEmits(['update:modelValue'])

const editor = useEditor({
  content: props.modelValue,
  extensions: [
    StarterKit,
    Placeholder.configure({
      placeholder: 'Your story...',
    }),
  ],
  editorProps: {
    attributes: {
      class:
        'prose prose-sm sm:prose lg:prose-lg xl:prose-2xl m-5 focus:outline-none',
    },
  },
  onCreate({ editor }) {
    const author = document.querySelector('#author')
    author.addEventListener('keypress', (event) => {
      if (event.keyCode === 13)
        // Focus on the editor on author click
        editor.view.dom.focus()
    })
  },
  onUpdate: ({ editor }) => {
    emit('update:modelValue', editor.getJSON())
  },
})
</script>

<template>
  <EditorContent :editor="editor" />
</template>

<style>
.ProseMirror:focus {
  outline: none;
}

.ProseMirror p.is-editor-empty:first-child::before {
  content: attr(data-placeholder);
  float: left;
  color: #adb5bd;
  pointer-events: none;
  height: 0;
}
</style>
