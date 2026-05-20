<template>
    <div class="w-full shadow-2xl rounded-xl flex flex-col gap-3 items-center pb-3">
        <img class="w-full rounded-t-xl" :src="profile.image">
        <h1 class="text-2xl font-bold">{{ profile.name }}</h1>
        <h1 class="text-xl font-bold">{{ profile.sex }}</h1>
        <h1 class="text-xl font-bold text-red-500">{{ profile.level }}</h1>
    </div>
</template>
<script setup>

    const myData = defineProps({
        profile:Object
    })

</script>