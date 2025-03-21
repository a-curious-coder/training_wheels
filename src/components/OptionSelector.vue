<template>
  <div>
    <Checkbox
      v-for="option in options"
      :label="option.label"
      :value="option.value"
      v-model:selectedValues="selectedValues"
    />
  </div>
</template>

<script setup lang="ts">
  import { watch } from 'vue'
import Checkbox from './Checkbox.vue';
import type Option from '../types/Option'

const selectedValues = defineModel('selectedValues', { type: Array<String> })

defineProps({
  options: {
    type: Array<Option>,
    required: true
  }
});

watch(selectedValues, (newX) => {
  console.log(`Selected Values are [${newX}]`)
})
</script>

<style scoped></style>
