<template>

    <div class="container w-125 rounded-2xl flex flex-col 
        justify-center items-center gap-5 p-5 shadow-2xl">

        <div class="title text-3xl font-bold">Find Someone</div>

        <form @submit.prevent="finding" class="w-full flex 
            justify-center items-center gap-3" action="">

            <input v-model="find" class="w-full px-3 py-4 rounded-xl 
                border border-gray-200 focus:outline-none focus:ring-2
                focus:ring-black hover:border-black transition" 
                type="text" placeholder="Enter name">

            <button class="w-[30%] rounded-xl bg-black text-white px-3 py-4
                hover:bg-gray-900 active:bg-black cursor-pointer" 
                type="submit">Find</button>

        </form>

        <!-- check mer item tha mean ot ber mean ban div(card-container) der -->
        <div v-if="result.length > 0" class="card-container w-full 
            h-80 overflow-y-auto scrollbar-none grid grid-cols-2 
            place-items-center ">

            <div v-for="person in result" :key="person.id" 
                class="w-50 rounded-2xl border border-gray-200 my-3.5">
    
                <img
                    class="w-full h-48 object-cover rounded-t-xl"
                    :src="person.image"
                    alt="profile"
                />

                <div class="p-4 flex flex-col gap-3">

                    <h2 class="text-xl font-bold">{{person.name}}</h2>

                    <button class="bg-black text-white py-2 rounded-xl 
                        hover:bg-gray-900 active:bg-black 
                        transition">View</button>

                </div>

            </div>
        </div>

        <div v-else class="w-full flex justify-center items-center text-2xl">
            No name found
        </div>

    </div> 
  
</template>

<script setup>

    import { ref } from 'vue';

    const find = ref("")
    const result = ref([])

    const profile = ref([
        { id: 1, image: "/img/img1.jpg", name: "Yan Phayu" },
        { id: 2, image: "/img/img2.jpg", name: "Sok Dara" },
        { id: 3, image: "/img/img3.jpg", name: "Lina Chenda" },
        { id: 4, image: "/img/img4.jpg", name: "Vannak Rith" },
        { id: 5, image: "/img/img5.jpg", name: "Pisey Nika" },
        { id: 6, image: "/img/img6.jpg", name: "Chantha Srey" },
        { id: 7, image: "/img/img7.jpg", name: "Kosal Veasna" },
        { id: 8, image: "/img/img8.jpg", name: "Ralis Kiri" },
        { id: 9, image: "/img/img9.jpg", name: "Dalin Sovann" },
        { id: 10, image: "/img/img10.jpg", name: "Ravy Pich" }
    ]);

    const finding = () => {

        const query = find.value.trim().toLowerCase();

        if (!query) {
            result.value = [];
            return;
        }

        if (query !== "show all"){
            result.value = profile.value.filter((person) =>
                person.name.toLowerCase().includes(query)
            );
        }
        else{
            result.value = profile.value;
        }
    };

</script>
