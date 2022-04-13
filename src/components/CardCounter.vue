<template>
  <div :class="count > 0 ? 'bg-purple-200' : 'bg-red-300'" class="flex justify-center items-center h-36 w-36 rounded text-9xl font-semibold">
    {{ count }}
  </div>
  double count: {{ counterStore.doubleCount}}
</template>

<script setup>
import { computed } from 'vue'
import { useCounterStore } from '../../stores/counter'

const counterStore = useCounterStore()
const count = computed(() => counterStore.count)
</script>
