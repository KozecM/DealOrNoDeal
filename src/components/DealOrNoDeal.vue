<script setup>
import { computed } from 'vue'
defineProps({
  boxes: {
    type: Array,
    required: true
  }
})
const deal = computed(() => {
  total_lost = 0
  for (box in props.boxes){
    total_lost += box
  }
  return total_lost
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ boxes }}</h1>
    <h3>
      The Dealer is offering: $ 
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
