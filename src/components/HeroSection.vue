<template>
  <section class="hero">
    <div ref="lottieContainer" class="lottie-bg"></div>
    <div class="hero-content">
      <h1 class="heading">
        <span class="intro-wrapper">
          <span class="intro-text">Hello, I'm</span>
          <span class="typewriter">Austin</span>
        </span>
      </h1>
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
