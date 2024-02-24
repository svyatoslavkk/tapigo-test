<template>
  <div class="flex flex-col gap-32 bg-gradient-to-b from-custom-color-111827 to-custom-color-1F293E w-full p-5 font-arboria-medium md:px-[60px] py-[144px]">
    <div v-for="(item, index) in items" :key="index" class="flex flex-col gap-8 md:flex-row  md:gap-16">
      <template v-if="index % 2 !== 0">
        <img :src="item.image" class="rounded-lg max-w-3xl max-h-xl object-cover object-center md:w-1/2" />
        <div class="relative flex flex-col justify-center gap-8 md:w-1/2 md:px-[48px]">
          <h2 class="text-2xl md:text-4xl leading-10 tracking-wide text-white font-semibold">{{ item.header }}</h2>
          <p class="text-base leading-6 text-gray-300 font-normal">{{ item.description }}</p>
          <button class="flex items-center gap-2">
            <span class="text-custom-color-6366F1 text-base leading-6 font-medium">{{ item.buttonText }}</span>
            <ArrowIcon />
          </button>
        </div>
      </template>
      <template v-else>
        <div class="relative flex flex-col justify-center gap-8 md:w-1/2 md:px-[48px]">
          <h2 class="text-2xl md:text-4xl leading-10 tracking-wide text-white font-semibold">{{ item.header }}</h2>
          <p class="text-base leading-6 text-gray-300 font-normal">{{ item.description }}</p>
          <button class="flex items-center gap-2">
            <span class="text-custom-color-6366F1 text-base leading-6 font-medium">{{ item.buttonText }}</span>
            <ArrowIcon />
          </button>
        </div>
        <img :src="item.image" class="image rounded-lg  max-w-800 max-h-560 object-cover object-center md:w-1/2" />
      </template>
    </div>
  </div>
</template>

<script>
import { items } from '~/constants';

export default {
  data() {
    return {
      items: items,
    };
  },
  components: {
  },
};
</script>

<style>
  
</style>