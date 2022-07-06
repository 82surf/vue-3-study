<template>
  <button @click="increment">count {{ state.count }}</button>
  <br />
  <button @click="mutateDeeply">
    deep mutation test {{ obj.nested.count }}
  </button>
  <ul>
    <li v-for="val in obj.arr" :key="val">{{ val }}</li>
  </ul>
  <br />
  <!-- ref로 생성한 state는 자동으로 unwrapping 됩니다. .value 쓸 필요 없음! -->
  <button @click="incrementRef">ref test {{ count }}</button>
  <br />
  <p>{{ object.foo.value + 1 }}</p>
  <p>{{ foo }}</p>
</template>

<script setup>
import { reactive, ref } from 'vue';

// reactive state는 reactive()로 선언할 수 있다.
// reactive state는 proxy 객체로 raw 객체와 다르다.
const state = reactive({ count: 0 });

function increment() {
  state.count++;
}

// reactive state는 객체 내부의 property의 변경사항도 감지한다.
// reactive state는 객체 타입(object, array, Map, Set)에만 적용할 수 있다.
const obj = reactive({
  nested: { count: 0 },
  arr: ['foo', 'bar'],
});

function mutateDeeply() {
  obj.nested.count++;
  obj.arr.push('baz');
}

// 어떤 자료형이든 reactive state로 관리할 수 있는 ref()도 있다.
const count = ref(0);
console.log(count);
console.log(count.value);

function incrementRef() {
  count.value++;
}

const object = { foo: ref(1) };
const { foo } = object;
console.log(foo);
console.log(foo.value);
</script>

<style></style>
