<template>
  <nav class="navbar">
    <RouterLink to="/" class="brand-link">
      <h3>AUSTIN HENRY</h3>
      <!--Add typerwriter effect for name-->
    </RouterLink>
    <button>
      <span class="label">MENU</span>
      <span class="dot"></span>
    </button>
  </nav>
</template>

<script setup>
import { RouterLink } from "vue-router";
</script>
