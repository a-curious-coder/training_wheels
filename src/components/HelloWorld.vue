<template>
  <OptionSelector
    :options
    v-model:selectedValues="selectedValues"
  />
  <div class="message">
    <p v-if="selectedValues.length > 0">You selected: {{ selectedValues }}</p>
    <p v-else>Please select an option</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import OptionSelector from './OptionSelector.vue'

const options = [
  { 'label': 'Option 1', 'value': 'Value 1' },
  { 'label': 'Option 2', 'value': 'Value 2' },
  { 'label': 'Option 3', 'value': 'Value 3' },
  { 'label': 'Option 4', 'value': 'Value 4' },
]

const selectedValues = ref([]);
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
