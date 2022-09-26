<script lang="ts">
export default {
  name: "SlideTwo",
};
</script>
<script setup lang="ts"></script>

<template>
  <div class="wrapper">
    <div
      swiper-animate-effect="bounceInLeft"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
      class="ani"
    >
      年度总结2
    </div>
    <div
      swiper-animate-effect="bounceInLeft"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
      class="ani"
    >
      年度总结2
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
