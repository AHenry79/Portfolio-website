<template>
  <CustomCursor />
  <AppNavbar />
  <RouterView />
</template>

<script setup>
import { RouterView } from "vue-router";
import CustomCursor from "@/components/CustomCursor.vue";
import AppNavbar from "@/components/AppNavbar.vue";
</script>
