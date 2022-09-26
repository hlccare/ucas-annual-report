<script lang="ts">
export default {
  name: "SlideFive",
};
</script>
<script setup lang="ts"></script>

<template>
  <div class="wrapper">
    <div
      class="ani"
      swiper-animate-effect="shake"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
    >
      年度总结5
    </div>
    <div
      class="ani"
      swiper-animate-effect="tada"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
    >
      年度总结5
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
