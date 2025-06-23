<template>
  <div :style="cursorStyle" class="custom-cursor"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed } from "vue";

const x = ref(0);
const y = ref(0);
let isHovered = ref(false);

const cursorStyle = computed(() => ({
  left: `${x.value}px`,
  top: `${y.value}px`,
  transform: "translate(-50%, -50%)",
  backgroundColor: isHovered.value ? "#4a9a8c" : "transparent",
  width: isHovered.value ? "15px" : "30px",
  height: isHovered.value ? "15px" : "30px",
}));

function updateCursor(e) {
  x.value = e.clientX;
  y.value = e.clientY;
}

onMounted(() => {
  document.addEventListener("mousemove", updateCursor);

  document.addEventListener("mouseover", (e) => {
    const target = e.target.closest("a, button");
    if (target) isHovered.value = true;
  });

  document.addEventListener("mouseout", (e) => {
    const related = e.relatedTarget;
    const leavingFrom = e.target.closest("a, button");
    const enteringInto = related?.closest?.("a, button");

    // Only turn off hover if we're leaving the entire interactive element
    if (leavingFrom && leavingFrom !== enteringInto) {
      isHovered.value = false;
    }
  });
});

onUnmounted(() => {
  document.removeEventListener("mousemove", updateCursor);
});
</script>
