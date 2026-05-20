<template>
  <div
    class="w-200 rounded-2xl shadow-2xl bg-blue-50 p-5 flex flex-col gap-10 overflow-y-scroll scrollbar-none"
  >
    <!-- header -->
    <h1 class="text-blue-600 text-3xl font-bold text-center">Manage These</h1>
    <!-- option -->
    <div class="w-full flex gap-10 px-7">
      <!-- ADD -->
      <button
        class="w-[40%] text-xl bg-green-700 hover:bg-green-600 active:bg-green-700 px-3 py-2 rounded-xl text-white"
        @click="openModal"
      >
        ADD
      </button>
      <!-- search -->
      <div class="w-[60%] flex gap-5">
        <input
          class="w-[70%] text-xl bg-white rounded-xl px-3 outline-blue-700"
          type="text"
          placeholder="Search"
        />
        <button
          class="w-[30%] text-xl bg-blue-700 hover:bg-blue-600 active:bg-blue-700 px-3 py-2 rounded-xl text-white"
        >
          Search
        </button>
      </div>
    </div>
    <!-- card -->
    <div class="w-full h-80 grid grid-cols-3 gap-2 place-items-center">
      <Child
        v-for="item in profile"
        :key="item.id"
        :profile="item"
        @myDelete="handleDelete"
      />
    </div>
  </div>
  <!-- Modal -->
  <div
    v-if="isModal"
    @click.self="closeModal"
    class="w-full h-full bg-black/15 fixed top-0 left-0 z-50 flex justify-center items-center"
  >
    <div class="w-fit flex flex-col gap-10 bg-blue-50 rounded-xl p-10">
      <input
        v-model="newid"
        class="w-full text-xl bg-white rounded-xl px-3 py-2 outline-blue-700"
        type="text"
        placeholder="ID"
      />
      <input
        v-model="newimage"
        class="w-full text-xl bg-white rounded-xl px-3 py-2 outline-blue-700"
        type="text"
        placeholder="Image address"
      />
      <input
        v-model="newname"
        class="w-full text-xl bg-white rounded-xl px-3 py-2 outline-blue-700"
        type="text"
        placeholder="Name"
      />
      <div class="w-full flex gap-5 justify-center items-baseline-last">
        <button
          class="w-full text-xl bg-green-700 hover:bg-green-600 active:bg-green-700 px-3 py-2 rounded-xl text-white"
          @click="handleADD"
        >
          ADD
        </button>
        <button
          class="w-full text-xl bg-red-700 hover:bg-red-600 active:bg-red-700 px-3 py-2 rounded-xl text-white"
          @click="closeModal"
        >
          Cancel
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Child from "./Child.vue";

const profile = ref([
//   {
//     id: "001",
//     image:
//       "https://i.pinimg.com/736x/5e/dc/fd/5edcfd38085e895176d895b7681c33ca.jpg",
//     name: "Yan Phayu",
//   },
]);

function handleDelete(id) {
  profile.value = profile.value.filter((item) => item.id !== id);
}

let isModal = ref(false);

function openModal() {
  isModal.value = true;
}
let newid = ref("");
let newimage = ref("");
let newname = ref("");
function handleADD() {
  if (!newid.value || !newimage.value || !newname.value) return;

  profile.value.push({
    id: newid.value,
    image: newimage.value,
    name: newname.value,
  });

  newid = ref("");
  newimage = ref("");
  newname = ref("");

  isModal.value = false;
}

function closeModal() {
  isModal.value = false;
}
</script>
