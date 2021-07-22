<template>
  <div class="counter">
    <button @click="subtract()">-</button>
    <pre>{{ count }}</pre>
    <button @click="add()">+</button>
  </div>
  <div class="children">
    <Children />
  </div>
</template>

<script>
import { ref } from 'vue';

import Children from './Children.vue';

export default {
  components: {
    Children
  },
  setup() {
    const count = ref(0);
    const add = () => (count.value = count.value + 1);
    const subtract = () => (count.value = count.value - 1);
    return {
      count,
      add,
      subtract,
    };
  },
};
</script>
