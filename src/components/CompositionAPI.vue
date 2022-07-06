<template>
  <h3>Counter</h3>
  <button @click="increment">increment</button>
  <p>count: {{ count }}</p>
  <hr />
  <h3>Add item</h3>
  <button @click="addItem">Add Item</button>
  <ul>
    <li v-for="item in items.arr" :key="item">{{ item }}</li>
  </ul>
</template>

<script setup>
// Composition API
import { ref, reactive } from 'vue';

// Counter Logic
// state
const count = ref(0);
// method
function increment() {
  count.value++;
}

// Add Item Logic
// state
const items = reactive({ arr: ['foo', 'bar'] });
// method
function addItem() {
  items.arr.push('new item');
}
</script>

<style></style>
