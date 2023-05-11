<script setup>
import {computed, ref} from 'vue'
import { useCounterStore } from '@/stores/counter'

const storeCounter = useCounterStore()

const count = ref(0)

  const increaseCount = () => {
    count.value++
  }
  const decreaseCount = () => {
    count.value--
  }

  const oddOrEven = computed(() => {
    if (count.value % 2 === 0) return 'even'
    return 'odd'
  })
</script>
<template>
  <div class="home">
      <div class="count">
	      {{ storeCounter.count }}
      </div>
      <div class="button">
	      <button @click="storeCounter.decreaseCount">-</button>
	      <button @click="storeCounter.increaseCount">+</button>
      </div>
      <div>
          This counter is: {{ oddOrEven }}
      </div>
  </div>
</template>
<style>
.count {
    font-size: 60px;
    margin: 20px;
}
.buttons button {
    font-size: 40px;
    margin: 10px;
}
</style>
