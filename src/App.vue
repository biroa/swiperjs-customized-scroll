<template>
  <div style="width: 200px;">
    <!-- :mousewheel="true"         :loopFillGroupWithBlank="true" -->
    <swiper
        :direction="'vertical'"
        :navigation="true"
        :slidesPerView="4"
        :spaceBetween="30"
        :watchSlidesProgress="true"
        :slideToClickedSlide="true"
        :loop="true"
        :modules="modules"
        class="mySwiper"
    >
      <swiper-slide :style="{backgroundColor:mycolor(1)}">Slide 1</swiper-slide>
      <swiper-slide :style="{backgroundColor:mycolor}">Slide 2
      </swiper-slide
      >
      <swiper-slide :style="{backgroundColor:mycolor(2)}">Slide 3</swiper-slide>
      <swiper-slide :style="{backgroundColor:mycolor(3)}">Slide 4
      </swiper-slide
      >
      <swiper-slide :style="{backgroundColor:mycolor(4)}">Slide 5</swiper-slide>
      <swiper-slide :style="{backgroundColor:mycolor(5)}">Slide 6
      </swiper-slide
      >
      <swiper-slide :style="{backgroundColor:mycolor(6)}">Slide 7</swiper-slide>
      <swiper-slide :style="{backgroundColor:mycolor(7)}">Slide 8
      </swiper-slide
      >
    </swiper>
  </div>
</template>
<script>
// Import Swiper Vue.js components
import {Swiper, SwiperSlide} from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";
import "swiper/css/navigation";

import "./style.css";

// import required modules
import {Pagination, Mousewheel, Navigation} from "swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  methods:{
    mycolor(num){
      return  '#'+(num + Math.random()*0xFFFFFF<<0).toString(16);
    }
  },
  setup() {
    return {
      modules: [Pagination, Mousewheel, Navigation],
    };
  },
};
</script>
<style>
.swiper-slide{
  background-color: red;
}

.swiper-vertical .swiper-button-next, .swiper-vertical .swiper-button-prev {
  left: 50%;
  transform: rotate(90deg);
  transform-origin: left center;
}
.swiper-vertical .swiper-button-prev {
  top: 10px;
}
.swiper-vertical .swiper-button-next {
  top: auto;
  bottom: 10px;
}


</style>
