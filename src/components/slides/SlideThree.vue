<script lang="ts">
export default {
  name: "SlideThree",
};
</script>
<script setup lang="ts"></script>

<template>
  <div class="wrapper">
    <div
      class="ani"
      swiper-animate-effect="fadeInUp"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
    >
      年度总结3
    </div>
    <div
      class="ani"
      swiper-animate-effect="bounceInRight"
      swiper-animate-duration="1s"
      swiper-animate-delay="0s"
    >
      年度总结3
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
