<template>
  <div class="quizes">
    <div class="quizes-pagination"></div>
    <swiper
      :slides-per-view="1"
      :space-between="50"
      :modules="[Pagination]"
      :pagination="{
        el: '.quizes-pagination',
        clickable: true,
        renderBullet: function (index, className) {
          return `<button class='${className} text-slate-500 font-normal text-sm'> ${tests[index].science} </button>`;
        },
      }"
    >
      <swiper-slide v-for="subject in tests" :key="subject.id">
        <div class="quizes__container">
          <div class="quiz" v-for="quiz in subject.sub" :key="quiz.id">
            <div class="quiz__row">
              <div class="quiz__image"></div>
              <div class="quiz__main">
                <p class="quiz__title">{{ quiz.name }}</p>
                <p class="quiz__info">
                  <img src="~/assets/images/icons/file.svg" alt="file" />
                  10 Question
                </p>
              </div>
              <div class="quiz__rate">
                <img src="~/assets/images/icons/star.svg" alt="rate" />
                <p>4.8</p>
              </div>
            </div>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper/modules';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/pagination';

// debug tests
import { tests } from '../db/tests.js';
</script>

<style lang="scss" scoped></style>
