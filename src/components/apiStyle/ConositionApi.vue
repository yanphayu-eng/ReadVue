<template>
  <div class="w-fit shadow-xl rounded-2xl p-2">
    <img :src="profile" class="rounded-2xl">
    <h3 class="text-3xl text-center font-bold">{{ name }}</h3>
    <h4 class="text-2xl text-center">{{ level }}</h4>

    <h4 
      @click="level++"
      class="text-2xl text-center cursor-pointer"
    >
      {{ status }}
    </h4>
  </div>
</template>

<script setup>
import { ref } from 'vue';

    const profile = ref('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRnIfGlc3kfthu8ciB3noIMBkTdpHAozyjgZg&s');
    const name = ref('Super Dark');
    const level = ref(99);
    const status = ref((level.value > 18)? 'Legend' : 'Noob');

</script>
