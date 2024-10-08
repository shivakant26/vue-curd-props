<script setup>
import Hellow from '@/components/Hellow.vue';
import { ref } from 'vue';
const count = ref(0);
function myCounter(n) {
  count.value += n
}
</script>
<template>
  <div class="about">
    <div class="center-wr">
      <h1>Example of parent to child Data Transfer</h1>
      <h2>Count : {{ count }}</h2>
      <!-- <Hellow @increaseCount="count++" title="Child Component" /> -->
      <Hellow @increase-count="myCounter" title="Child Component" />
    </div>
  </div>
</template>

<style scoped>
.about {
  width: 500px;
  border: 1px solid gray;
  padding: 12px;
}

.center-wr {
  width: 1200px;
  margin: 0 auto;
}
</style>
