<template>
  <form @submit.prevent="searching">
    <input v-model="search" type="search" placeholder="Enter name" />
    <button>Search</button>
  </form>

  <!-- Show only when results exist -->
  <ul v-if="result.length > 0">
    <li v-for="n in result" :key="n.id">
      {{ n.name }}
    </li>
  </ul>

  <!-- Show when no match found -->
  <p v-else-if="searched">
    No name found
  </p>
</template>

<script setup>
import { ref } from "vue";

const search = ref("");
const searched = ref(false);

const name = ref([
  { id: 1, name: "Yan Phayu" },
  { id: 2, name: "Sok Dara" },
  { id: 3, name: "Chanthy Rina" },
  { id: 4, name: "Vannak Sopheak" },
  { id: 5, name: "Kimly Chenda" },
  { id: 6, name: "Piseth Sovann" },
  { id: 7, name: "Nary Sreyneang" },
  { id: 8, name: "Bora Vichea" },
  { id: 9, name: "Sokha Monika" },
  { id: 10, name: "Rithy Dara" },
  { id: 11, name: "Sreypov Lin" },
  { id: 12, name: "Makara Sopheaktra" },
  { id: 13, name: "Channy Ratanak" },
  { id: 14, name: "Vicheka Sovanara" },
  { id: 15, name: "Danechka Mey" },
  { id: 16, name: "Pisey Rotha" },
  { id: 17, name: "Sokun Theara" },
  { id: 18, name: "Chhean Dara" },
  { id: 19, name: "Leakhena Sovan" },
  { id: 20, name: "Vannarin Sreyneang" }
]);

const result = ref([]);

function searching() {
  searched.value = true;

  const query = search.value.trim();

  console.log(!query)

  if(!query){
    result.value = []
    return;
  }

  result.value = name.value.filter((n) =>
    n.name.toUpperCase().includes(search.value.toUpperCase())
  );
}
</script>