<template>
    <div class="w-80 rounded-2xl shadow-2xl bg-cyan-50 p-5 
        flex flex-col gap-5">
        <h1 class="text-blue-700 text-3xl 
        font-bold text-center">Click This</h1>
        <button @click="handleClick" class="bg-blue-700
         hover:bg-blue-600 active:bg-blue-700 px-3 py-2
          rounded-xl text-xl text-cyan-50 w-full">Click</button>
        <h1 class="text-blue-600 
        text-2xl font-bold text-center">{{ count }}</h1>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    let emit = defineEmits(['myEmit']);
    defineProps({count:Number});
    function handleClick(){
        emit('myEmit',1);
    }

</script>