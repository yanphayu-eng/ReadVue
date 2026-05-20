<template>

    <!-- Changed flex-column to flex-col -->
<div class="flex flex-col justify-center w-fit border-2 rounded-2xl p-3 gap-3">

    <h1 class="text-3xl text-red-500 font-bold">Click Counter</h1>
    <p>Count : {{ count }}</p>
    
    <!-- Changed w-100 to w-full -->
    <button 
        class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded-2xl active:bg-red-500 w-full" 
        @click="count++">
        Click
    </button>

</div>

  
</template>

<script setup>

    import { ref } from 'vue';

    const count = ref(0);

</script>
