<template>
  <h1 class="text-5xl font-bold text-amber-400">Say : {{ txt }}</h1>
</template>

<script setup>
    defineProps({
        txt:String
    })
</script>