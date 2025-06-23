<template>
  <section class="hero">
    <div ref="lottieContainer" class="lottie-bg"></div>
    <div class="hero-content">
      <h1>Hello, I'm Austin</h1>
      <p>Application & Software Engineer</p>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from "vue";
import Lottie from "lottie-web";

const lottieContainer = ref(null);

onMounted(() => {
  Lottie.loadAnimation({
    container: lottieContainer.value,
    renderer: "svg",
    loop: true,
    autoplay: true,
    path: "/animations/HeroSectionAnimation.json", // Update this if needed
    rendererSettings: {
      preserveAspectRatio: "xMidYMid slice", // fills container while preserving aspect
    },
  });
});
</script>
