<template>
  <div class="settings">
    <UTabs :items="tabs" :default-index="0" >
      <template #item="{ item }">
        <div v-if="item.key === 'quantity'" class="space-y-3">
          <div class="settings__item mt-5">
            <p class="settings__text">Sonini tanlang</p>
            <USelect
              color="blue"
              variant="outline"
              :options="['10', '20', '30']"
              model-value="10"
            />
          </div>
          <div class="settings__item">
            <p class="settings__text">Qiyinlikni tanlang</p>
            <USelect
              color="blue"
              variant="outline"
              :options="['Oson', 'O`rta', 'Qiyin']"
              model-value="Oson"
            />
          </div>
        </div>
        <div v-if="item.key === 'time'" class="space-y-3">
          <div class="settings__item mt-5">
            <p class="settings__text">Vaqtni tanlang</p>
            <USelect
              color="blue"
              variant="outline"
              :options="['5m', '10m', '20m']"
              model-value="5m"
            />
          </div>
          <div class="settings__item">
            <p class="settings__text">Qiyinlikni tanlang</p>
            <USelect
              color="blue"
              variant="outline"
              :options="['Oson', 'O`rta', 'Qiyin']"
              model-value="Oson"
            />
          </div>
        </div>
      </template>
    </UTabs>
  </div>
</template>

<script setup>
const tabs = [
  {
    key: 'quantity',
    label: 'Quantity',
    description: '',
  },
  {
    key: 'time',
    label: 'Time',
    description:
      "Change your password here. After saving, you'll be logged out.",
  },
];

const items = [
  [
    {
      label: 'Profile',
      avatar: {
        src: 'https://avatars.githubusercontent.com/u/739984?v=4',
      },
    },
  ],
  [
    {
      label: 'Edit',
      icon: 'i-heroicons-pencil-square-20-solid',
      shortcuts: ['E'],
      click: () => {
        console.log('Edit');
      },
    },
    {
      label: 'Duplicate',
      icon: 'i-heroicons-document-duplicate-20-solid',
      shortcuts: ['D'],
      disabled: true,
    },
  ],
  [
    {
      label: 'Archive',
      icon: 'i-heroicons-archive-box-20-solid',
    },
    {
      label: 'Move',
      icon: 'i-heroicons-arrow-right-circle-20-solid',
    },
  ],
  [
    {
      label: 'Delete',
      icon: 'i-heroicons-trash-20-solid',
      shortcuts: ['⌘', 'D'],
    },
  ],
];
</script>

<style lang="scss" scoped></style>
