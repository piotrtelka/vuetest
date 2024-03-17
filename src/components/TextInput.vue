<template>
  <label class="text-input">
    {{label}}
    <input type="text" v-model="value">
  </label>
</template>

<script setup>
import {computed} from "vue";

const props = defineProps(['label', 'modelValue', 'validate'])
const emits = defineEmits(['update:modelValue'])

const value = computed({
  get: () => props.modelValue,
  set: (newVal) => emits('update:modelValue', newVal)
})
</script>

<style scoped>
.text-input {
  display: flex;
  flex-direction: column;
}

input {
  height: 30px;
}
</style>
