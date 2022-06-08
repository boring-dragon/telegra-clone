<script setup lang="ts">
const props = defineProps({
  modelValue: {
    required: true,
  },
  placeholder: {
    type: String,
    default: 'eyo write something..',
  },
})

function resize(e) {
  e.target.style.height = 'auto'
  e.target.style.height = `${e.target.scrollHeight}px`
}
</script>

<template>
  <textarea class="w-full border-none focus:outline-0 resize-none leading-[42px]" rows="2" :placeholder="props.placeholder" :value="props.modelValue" @input="$emit('update:modelValue', $event.target.value); resize($event)" />
</template>
