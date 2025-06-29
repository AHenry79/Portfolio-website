<template>
  <nav class="navbar">
    <RouterLink
      to="/"
      class="brand-link"
      :disabled="isMenuOpen"
      :class="{ disabled: isMenuOpen }"
    >
      <h3>AUSTIN HENRY</h3>
    </RouterLink>
    <button @click="toggleMenu">
      <span
        v-if="!isMenuOpen"
        :class="{ active: !isMenuOpen }"
        class="label menu-text"
        >MENU</span
      >
      <span v-else class="label close-text" :class="{ active: isMenuOpen }"
        >CLOSE</span
      >
      <span class="dot"></span>
    </button>
  </nav>
  <!-- Full screen overlay -->
  <transition name="fade">
    <div v-show="isMenuOpen" class="menu-overlay">
      <div class="menu-container"></div>
    </div>
  </transition>
</template>

<script setup>
import { RouterLink } from "vue-router";
import { ref } from "vue";

const isMenuOpen = ref(false);

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}
</script>
