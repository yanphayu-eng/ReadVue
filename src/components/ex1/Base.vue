<template>
    <div class="w-100 md:w-125 h-125 shadow-2xl rounded-2xl grid grid-cols-1 
    md:grid-cols-2 gap-5 overflow-y-scroll p-10 scrollbar-none">
        <Child v-for="items in arr" :key="items.id" :profile="items"/>
    </div>
</template>
<script setup>
import { ref } from 'vue';
import Child from './Child.vue';

    const arr = ref([
        {id:"001",sex:"God",level:"999",name:"Yan Phayu",image:"/img/img1.jpg"},
        {id:"002",sex:"God",level:"999",name:"Yan Vannak",image:"/img/img2.jpg"},
        {id:"003",sex:"God",level:"999",name:"Hak Kai",image:"/img/img3.jpg"},
        {id:"004",sex:"God",level:"999",name:"Sen Hong",image:"/img/img4.jpg"},
        {id:"005",sex:"God",level:"999",name:"Lai XiXi",image:"/img/img5.jpg"},
        {id:"006",sex:"God",level:"999",name:"Vey RiKong",image:"/img/img6.jpg"},
        {id:"007",sex:"God",level:"999",name:"Tan SeavLak",image:"/img/img7.jpg"},
        {id:"008",sex:"God",level:"999",name:"Song GiGi",image:"/img/img8.jpg"},
        {id:"009",sex:"God",level:"999",name:"Zin Siyok",image:"/img/img9.jpg"},
        {id:"010",sex:"God",level:"999",name:"Ben Kam",image:"/img/img10.jpg"},
    ])
</script>