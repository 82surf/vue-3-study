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
export default {
  data() {
    return {
      count: 1,
      items: ['foo', 'bar'],
    };
  },
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
