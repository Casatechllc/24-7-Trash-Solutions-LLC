<template>
  <section class="carousel-section py-5">
    <div class="container">
      
      <div class="text-center mb-3" data-aos="fade-up">
        <h2 class="fw-bold">See Our Dumpsters in Action</h2>
        <div style="width: 60px; height: 4px; background: #d4af37; margin: 10px auto;"></div>
        <p>Clean, reliable 13-yard containers ready for your next project.</p>
      </div>

      <swiper
        :modules="modules"
        :slides-per-view="1"
        :space-between="30"
        :loop="true"
        :pagination="{ clickable: true }"
        :navigation="true"
        :autoplay="{ delay: 4000, disableOnInteraction: false }"
        class="mySwiper pb-5"
      >
        <swiper-slide v-for="item in slides" :key="item.id">
          
          <div class="slide-content shadow-lg rounded overflow-hidden position-relative">
            <img :src="item.image" :alt="item.alt" class="swiper-img" />
            
            <!-- <div class="caption-overlay">
              <h5 class="m-0 text-white">{{ item.alt }}</h5>
            </div> -->
          </div>

        </swiper-slide>
      </swiper>

    </div>
  </section>
</template>

<script>
// 1. Import Swiper and Modules
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';

// 2. Import Swiper CSS
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

// 3. Import Data
import { carouselData } from '@/assets/data/carousel.js';

export default {
  name: 'ImageCarousel',
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      slides: carouselData,
      modules: [Navigation, Pagination, Autoplay],
    };
  },
};
</script>

<style scoped>
h2 {
    color: var(--light-text);
}

p {
    color: var(--light-text);
}
/* 1. Container Sizing */
.mySwiper {
  max-width: 900px;
  width: 100%;
  /* This padding creates space for arrows to sit "outside" the slides 
     without getting cut off by overflow:hidden */
  padding-left: 50px;
  padding-right: 50px;
}

/* 2. Image Styling */
.slide-content {
  position: relative;
  border-radius: 10px;
}

.swiper-img {
  width: 100%;
  height: 450px;
  object-fit: cover;
  display: block;
}

/* 3. Caption Styling */
.caption-overlay {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  background-color: rgba(0, 0, 0, 0.6);
  padding: 10px 20px;
  border-radius: 5px;
  width: max-content;
  max-width: 90%;
}

/* 4. OVERRIDE SWIPER COLORS (The Magic Part) */
:deep(.swiper-button-next),
:deep(.swiper-button-prev) {
  color: #d4af37; /* Gold Arrows */
  font-weight: bold;
}

:deep(.swiper-pagination-bullet-active) {
  background-color: #d4af37; /* Gold Active Dot */
}

/* 5. Mobile Adjustments */
@media (max-width: 768px) {
  .mySwiper {
    padding-left: 0;
    padding-right: 0;
  }
  
  .swiper-img {
    height: 300px;
  }
  
  /* On mobile, arrows often get in the way, so we can hide them 
     and rely on touch swiping + dots */
  :deep(.swiper-button-next),
  :deep(.swiper-button-prev) {
    display: none;
  }
}
</style>