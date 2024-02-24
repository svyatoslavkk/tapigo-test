<template>
  <div class="flex flex-col gap-32 bg-gradient-to-b from-custom-color-111827 to-custom-color-1F293E w-full p-5 font-arboria-medium">
    <div v-for="(item, index) in items" :key="index" class="flex flex-col gap-8">
      <img :src="item.image" class="rounded-lg" />
      <h2 class="text-2xl leading-10 tracking-wide text-white font-semibold">{{ item.header }}</h2>
      <p class="text-base leading-6 text-gray-300 font-normal">{{ item.description }}</p>
      <button class="flex items-center gap-2">
        <span class="text-custom-color-6366F1 text-base leading-6 font-medium">{{ item.buttonText }}</span>
        <ArrowIcon />
      </button>
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