<template>
  <div class="main">
    <div class="main__head">
      <div class="main__row">
        <button class="main__menu">
          <img src="~/assets/images/icons/menu.svg" alt="menu" />
        </button>
        <div class="main__user">
          <UDropdown
            :items="items"
            mode="hover"
            :popper="{ placement: 'bottom-start' }"
          >
            <img src="~/assets/images/icons/user.svg" alt="user" />
          </UDropdown>
        </div>
      </div>

      <p class="main__subTitle">Hello Alex</p>
      <h3 class="main__title">Let's test your knowledge</h3>
      <div class="main__search">
        <img src="~/assets/images/icons/search.svg" alt="seach" />
        <input type="text" name="search" id="search" class="" />
      </div>
    </div>

    <div class="main__body content">
      <button class="content__toggle"></button>

      <div class="content__quizes">
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
            <div class="content__container">
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

      <div class="content__submit">Settings</div>
    </div>
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

// dropdown items
const items = [
  [
    {
      label: 'Profile',
      avatar: {
        src: 'https://avatars.githubusercontent.com/u/739984?v=4',
      },
    },
  ],
];
</script>

<style lang="scss" scoped></style>
