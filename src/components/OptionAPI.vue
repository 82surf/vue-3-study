<template>
  <h3>Counter</h3>
  <button @click="increment">increment</button>
  <p>count: {{ count }}</p>
  <hr />
  <h3>Add item</h3>
  <button @click="addItem">Add Item</button>
  <ul>
    <li v-for="item in items" :key="item">{{ item }}</li>
  </ul>
</template>

<script>
/**
 * Options API
 * state 선언부와 methods 선언부가 나뉘어져 있다.
 * 여러 로직을 작성하게 되면 코드 흐름 파악이 어렵다.
 */
export default {
  // state 선언부
  data() {
    return {
      count: 1,
      items: ['foo', 'bar'],
    };
  },
  // method 선언부
  methods: {
    increment() {
      this.count++;
    },
    addItem() {
      this.items.push('new item');
    },
  },
};
</script>

<style></style>
