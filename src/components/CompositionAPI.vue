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
import { ref, reactive } from 'vue';

const count = ref(0);
function increment() {
  count.value++;
}

const items = reactive({ arr: ['foo', 'bar'] });
function addItem() {
  items.arr.push('new item');
}
</script>

<style></style>
