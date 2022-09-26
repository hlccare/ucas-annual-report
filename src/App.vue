<script setup lang="ts">
import SwiperClass, {
  Pagination,
  Navigation,
  Grid,
  Mousewheel,
  EffectCards,
} from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/effect-fade";
import "swiper/css/effect-flip";
import "swiper/css/effect-cards";

import { ref } from "vue";

let vSwiperRef: SwiperClass | null = null;
const vSwiperIndex = ref<number>();
const setVSwiperRef = (swiper: SwiperClass) => {
  vSwiperRef = swiper;
};
const updateVSwiperIndex = () => {
  vSwiperIndex.value = vSwiperRef?.activeIndex;
};

const modules = ref([Grid, Pagination, Navigation, Mousewheel, EffectCards]);
</script>

<template>
  <div class="wrapper">
    <swiper
      class="vertical-swiper"
      :modules="modules"
      :effect="'cards'"
      direction="vertical"
      :slides-per-view="1"
      :space-between="18"
      :mousewheel="true"
      @swiper="setVSwiperRef"
      @slide-change="updateVSwiperIndex"
    >
      <swiper-slide class="slide">
        <div>年度总结1</div>
      </swiper-slide>
      <swiper-slide class="slide slide-2">
        <div>年度总结2</div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div>年度总结3</div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div>年度总结4</div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div>年度总结5</div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div>年度总结6</div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<style scoped>
.wrapper {
  width: 100%;
  height: 100%;
}
.vertical-swiper {
  width: 100%;
  max-width: 480px;
  height: 100%;
  margin-bottom: 10px;
}
.slide {
  background-color: aqua;
}
.test {
  margin-top: 100px;
}
.slide-1 {
  background-color: antiquewhite;
  height: 100px;
}
.slide-2 {
  background-color: aquamarine;
}
.slide-3 {
  background-color: beige;
}
.slide-4 {
  background-color: orange;
}
</style>
