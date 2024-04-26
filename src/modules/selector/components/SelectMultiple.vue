<script setup lang="ts">
import "vue3-select-component/dist/style.css";

import { ref } from "vue";
import VueSelect from "vue3-select-component";

// When setting `is-multi` to `true`, the `v-model` should be an array of strings.
const selected = ref<string[]>([]);
</script>

<template>
    <VueSelect
      v-model="selected"
      :is-multi="true"
      :options="[
        
        { label: 'France', value: 'fr' },
        { label: 'USA', value: 'us' },
        { label: 'Germany', value: 'de' },
        { label: 'Italy', value: 'it' },
        { label: 'Spain', value: 'es' },
        { label: 'Colombia', value: 'co' },
        { label: 'Ecuador', value: 'ec' },
      ]"
    >
      <template #value="{ option }">
        <div class="custom-value">
          <img :src="`https://flagsapi.com/${option.value.toUpperCase()}/flat/24.png`" class="block w-6 h-auto">
          <span>{{ option.label }}</span>
        </div>
      </template>
  
      <template #option="{ option }">
        <p class="custom-option">
          {{ option.label }} <small>{{ option.value }}</small>
        </p>
      </template>
    </VueSelect>
  </template>

<style lang="css" scoped>
:deep(.vue-select .custom-value) {
  display: flex;
  align-items: center;
  gap: 6px;
}

:deep(.vue-select .custom-option) {
  display: flex;
  align-items: center;
  gap: 4px;
  color: #171717;
  font-weight: 500;
  font-size: 16px;
}

:deep(.vue-select .custom-option small) {
  color: #525252;
  font-weight: 500;
  font-size: 14px;
}
</style>