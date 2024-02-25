<template>
  <div class="flex flex-col gap-32 bg-gradient-to-b from-custom-color-111827 to-custom-color-1F293E w-full px-5 py-5 font-arboria-medium md:px-[60px] md:py-[144px]">
    <div v-for="(item, index) in items" :key="index" class="flex flex-col gap-8 hidden md:flex md:flex-row md:gap-16">
      <template v-if="index % 2 !== 0">
        <img :src="item.image" class="image rounded-lg max-w-3xl max-h-xl object-cover object-center md:w-1/2 md:min-h-[400px]" />
        <div class="relative flex flex-col justify-center gap-8 md:w-1/2 md:px-[48px]">
          <h2 class="text-2xl md:text-4xl leading-10 tracking-wide text-white font-semibold">{{ item.header }}</h2>
          <p class="text-base leading-6 text-gray-300 font-normal">{{ item.description }}</p>
          <button class="flex items-center gap-2">
            <span class="text-custom-color-6366F1 text-base leading-6 font-medium">{{ item.buttonText }}</span>
            <ArrowIcon />
          </button>
          <span class="absolute bottom-0 left-0 transform rotate-45 hidden xl:inline-block">
            <AngleIcon />
          </span>
          <span class="absolute top-0 right-0 transform rotate-[225deg] hidden xl:inline-block">
            <AngleIcon />
          </span>
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
          <span class="absolute top-0 left-0 rotate-[-225deg] hidden xl:inline-block">
            <AngleIcon />
          </span>
          <span class="absolute bottom-0 right-0 -rotate-45 hidden xl:inline-block">
            <AngleIcon />
          </span>
        </div>
        <img :src="item.image" class="image rounded-lg  max-w-800 max-h-560 object-cover object-center md:w-1/2 md:min-h-[400px]" />
      </template>
    </div>
    <div v-for="(item, index) in items" :key="index" class="flex flex-col gap-8 md:hidden">
      <img :src="item.image" class="image rounded-lg max-w-3xl max-h-xl object-cover object-center md:w-1/2 md:min-h-96" />
        <div class="relative flex flex-col justify-center gap-8 md:w-1/2 md:px-[48px]">
          <h2 class="text-2xl md:text-4xl leading-10 tracking-wide text-white font-semibold">{{ item.header }}</h2>
          <p class="text-base leading-6 text-gray-300 font-normal">{{ item.description }}</p>
          <button class="flex items-center gap-2">
            <span class="text-custom-color-6366F1 text-base leading-6 font-medium">{{ item.buttonText }}</span>
            <ArrowIcon />
          </button>
          <span class="absolute bottom-0 left-0 transform rotate-45 hidden xl:inline-block">
            <AngleIcon />
          </span>
          <span class="absolute top-0 right-0 transform rotate-[225deg] hidden xl:inline-block">
            <AngleIcon />
          </span>
        </div>
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