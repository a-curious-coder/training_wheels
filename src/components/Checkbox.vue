<template>
  <div class="checkbox-container">
    <label>
      <input 
        type="checkbox" 
        v-model="selectedValues"
        :checked="isChecked"
        :value="value"
        @change="triggerChange(value)"
      />
      <span>{{ label }}</span>
    </label>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'
const selectedValues = defineModel<String[]>('selectedValues', { default: [] });

const props = defineProps({
  value: { type: String, required: true },
  label: { type: String, default: '' }
});

const emit = defineEmits(['update:selectedValues']);

const isChecked = computed(() => {
  return selectedValues.value.includes(props.value);
});

const triggerChange = (val: string) => {
  if (val === "Value 4" && isChecked) {
    // If exclusive mode and this value was just checked
    selectedValues.value = selectedValues.value.filter(item => item === val);
  }
  // The standard checkbox behavior (add/remove from array) is handled by v-model
};
</script>

