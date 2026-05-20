<template>
  <div>
    <!-- Trigger button -->
    <button @click="openModal">Open Modal</button>

    <!-- Modal -->
    <div v-if="isOpen" class="modal-overlay" @click.self="closeModal">
      <div class="modal">
        <h2>Hello Modal</h2>
        <p>This is a simple Vue modal.</p>

        <button @click="closeModal">Close</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"

const isOpen = ref(false)

const openModal = () => {
  isOpen.value = true
}

const closeModal = () => {
  isOpen.value = false
}
</script>

<style>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  background: white;
  padding: 20px;
  border-radius: 8px;
  min-width: 300px;
}
</style>