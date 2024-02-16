<template>
<div id="testimonial">
    <h3 class="headingCarousel my-10">Trabajos realizados</h3>
</div>
  <Carousel class="mb-12">
    <Slide v-for="image in images" :key="image.id">
        <img :src="image.src " :alt="image.id">
    </Slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>
</template>
  
  <script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Pagination, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

import interior1 from '@/assets/interior1.png';
import vertical1 from '@/assets/vertical1.png';
import vertical2 from '@/assets/vertical2.png';
import vertical3 from '@/assets/vertical3.png';
import rehabilitacion1 from '@/assets/rehabilitacion1.png';

export default defineComponent({
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      images: [
        { id: 1, src: interior1},
        { id: 2, src: vertical1},
        { id: 3, src: rehabilitacion1},
        { id: 4, src: vertical2},
        { id: 5, src: vertical3},
      ],
    };
  },
});
</script>
  
  <style>
.carousel__item {
  min-height: 200px;
  width: 100%;
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}
.carousel__item img {
  max-width: 100%;
  height: auto;
}
</style>
  