<script setup lang="ts">
import { ref } from "vue";
const links = [
  {
    id: 1,
    link: "Link 1",
  },
  {
    id: 2,
    link: "Link 2",
  },
  {
    id: 3,
    link: "Link 3",
  },
];

const activeLink = ref<number | null>(null);
const setActive = (id: number) => {
  activeLink.value = id;
};
</script>

<template>
  <div class="flex justify-center items-center min-h-screen bg-gray-900">
    <div class="flex flex-col text-white">
      <button
        @click="setActive(item.id)"
        class="p-1 cursor-pointer"
        :class="{
          'bg-green-500 text-red-700 font-bold': activeLink === item.id,
          'hover:bg-gray-700': activeLink !== item.id,
        }"
        v-for="item in links"
        :key="item.id"
      >
        {{ item.link }}
      </button>
    </div>
  </div>
</template>
