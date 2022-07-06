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
/**
 * Composition API
 * 하나의 로직을 작성할 때 state와 methods를 오가면서 작업할 필요가 없습니다.
 * Typescript를 적용하기에도 용이한 구조입니다.
 */
import { ref, reactive } from 'vue';

// --------- Counter Logic
const count = ref(0);   // state
function increment() {  // method
  count.value++;
}

// --------- Add Item Logic
const items = reactive({ arr: ['foo', 'bar'] });  // state
function addItem() {                              // method
  items.arr.push('new item');
}
</script>

<style></style>
