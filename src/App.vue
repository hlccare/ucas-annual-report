<script setup lang="ts">
import * as swiperAni from "./assets/style/animate"; //根据自己的路径进行引入
import {
  SlideOne,
  SlideTwo,
  SlideThree,
  SlideFour,
  SlideFive,
  SlideSix,
} from "./components/slides/index";

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

import { nextTick, ref } from "vue";

let vSwiperRef: SwiperClass | null = null;
const vSwiperIndex = ref<number>();
const setVSwiperRef = (swiper: SwiperClass) => {
  vSwiperRef = swiper;
};
const updateVSwiperIndex = () => {
  vSwiperIndex.value = vSwiperRef?.activeIndex;
};

const handleSlideChangeTransitionStart = (swiper: SwiperClass) => {
  swiperAni.swiperAnimate(swiper);
};

const initFunc = (swiper: SwiperClass) => {
  nextTick(() => {
    swiperAni.swiperAnimateCache();
    swiperAni.swiperAnimate(swiper);
  });
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
      @init="initFunc"
      @swiper="setVSwiperRef"
      @slide-change="updateVSwiperIndex"
      @slide-change-transition-start="handleSlideChangeTransitionStart"
    >
      <swiper-slide class="slide slide-1">
        <slide-one />
      </swiper-slide>
      <swiper-slide class="slide slide-2">
        <slide-two />
      </swiper-slide>
      <swiper-slide class="slide slide-3">
        <slide-three />
      </swiper-slide>
      <swiper-slide class="slide slide-4">
        <slide-four />
      </swiper-slide>
      <swiper-slide class="slide slide-5">
        <slide-five />
      </swiper-slide>
      <swiper-slide class="slide slide-6">
        <slide-six />
      </swiper-slide>
    </swiper>
  </div>
</template>

<style scoped>
@import url("../src/assets/style/animate.min.css");

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
.slide-5 {
  background-color: indianred;
}

.slide-6 {
  background-color: steelblue;
}
</style>
