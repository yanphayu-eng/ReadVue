<template>
  <Child :count="count" @myEmit="handleMyEmit" />
</template>

<script setup>
import { ref } from "vue";
import Child from "./Child.vue";
let count = ref(0);
function handleMyEmit(c) {
  count.value += c;
}
</script>