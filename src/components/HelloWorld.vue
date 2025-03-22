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
  { 'label': 'Monday', 'value': 'Monday' },
  { 'label': 'Tuesday', 'value': 'Tuesday' },
  { 'label': 'Wednesday', 'value': 'Wednesday' },
  { 'label': 'Thursday', 'value': 'Thursday' },
  { 'label': 'Friday', 'value': 'Friday' },
  { 'label': 'Saturday', 'value': 'Saturday' },
  { 'label': "I'm flexible", 'value': "I'm flexible" },
]

const selectedValues = ref([]);
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
