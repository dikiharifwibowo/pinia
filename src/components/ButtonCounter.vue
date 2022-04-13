<template>
  <div class="flex gap-2">
    <button @click="increment" class="bg-violet-500 hover:bg-violet-600 px-5 py-2 text-sm leading-5 rounded-full font-semibold text-white">
      Increment +
    </button>
    <button @click="decrement" class="bg-orange-500 hover:bg-orange-600 px-5 py-2 text-sm leading-5 rounded-full font-semibold text-white">
      Decrement - 
    </button>
      <button @click="reset" class="bg-red-500 hover:bg-red-600 px-5 py-2 text-sm leading-5 rounded-full font-semibold text-white">
      Reset
    </button>
  </div>
</template>

<script setup>
import { useCounterStore } from '../../stores/counter'

const counterStore = useCounterStore()

// change the state of the store with actions
const increment = () => {
  counterStore.increment()
}
const decrement = () => {
  counterStore.decrement()
}
const reset = () => {
  counterStore.reset()
}

// change the state of the store with $patch
// const increment = () => {
//   counterStore.$patch({
//     count: counterStore.count + 1
//   })
// }
// const decrement = () => {
//   if(counterStore.count > 0) {
//     counterStore.$patch({
//       count: counterStore.count - 1
//     })
//   }
// }
// const reset = () => {
//   counterStore.$reset()
// }
counterStore.$subscribe((mutation, state) => {
  if(mutation.storeId === 'counter' && state.count > 5) {
    counterStore.reset()
  }
})
</script>
