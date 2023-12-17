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

    <div class="main__body content" ref="mainBody">
      <button class="content__toggle"></button>

      <div class="content__quizes">
       <quizes v-if="main"></quizes>
       <settings v-else></settings> 
      </div>

      <div class="content__footer">
        <button class="content__submit base-button" @click="nextSection">Settings</button>
      </div>
    </div>

  </div>
</template>

<script setup>


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




const main = ref(true)
const mainBody = ref(null)


function nextSection() {
  mainBody.value.classList.add('close')
  
  setTimeout(() => {
    main.value = false
    mainBody.value.classList.remove('close')
    
  }, 1000);
}
</script>

<style lang="scss" scoped></style>
