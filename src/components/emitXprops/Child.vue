<template>
  <div class="w-50 rounded-2xl border border-blue-200">
    <img
      class="w-full h-48 object-cover rounded-t-xl"
      :src="profile.image"
      alt="profile"
    />
    <div class="p-4 flex flex-col gap-3">
      <h2 class="text-xl font-bold">{{ profile.name }}</h2>

      <button
        @click="handleDelete"
        class="bg-red-700 text-white py-2 rounded-xl hover:bg-red-600 active:bg-red-700 transition"
      >
        Delete
      </button>
    </div>
  </div>
</template>
<script setup>
const emit = defineEmits(["myDelete"]);
const props = defineProps({
  profile: Object,
});
function handleDelete() {
  emit("myDelete", props.profile.id);
}
</script>
