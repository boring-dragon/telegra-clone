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
defineEmits(['update:modelValue'])
function resize(e) {
  e.target.style.height = 'auto'
  e.target.style.height = `${e.target.scrollHeight}px`
}
</script>

<template>
  <div class="flex">
    <label v-if="props.modelValue.length > 0" class="text-sm mr-2">{{ props.placeholder }}</label>
    <textarea class="w-full  px-2 focus:outline-0 resize-none leading-[42px]" :class="{ 'border-l border-gray-300': props.modelValue.length > 0 }" rows="2" :placeholder="props.placeholder" :value="props.modelValue" @input="$emit('update:modelValue', $event.target.value); resize($event)" />
  </div>
</template>
