<template>
  <header class="header">
    <div class="flex items-center gap-12">
      <SearchIcon />
      <button class="flex items-center gap-2 py-2 px-4 bg-custom-color-1F3B8B rounded-lg">
        <MenuIcon />
        <span class="text-white font-medium text-base">Сервисы</span>
      </button>
    </div>
    <div>
      <img :src="logo" class="logo" />
    </div>
    <div class="flex items-center gap-12">
      <button class="flex items-center gap-2 py-2 px-4 bg-custom-color-1F3B8B rounded-lg">
        <span class="text-white font-medium text-base">Разместить</span>
      </button>
      <LogoutIcon />
    </div>
  </header>
</template>

<script>
import { logo } from '~/constants';

export default {
  data() {
    return {
      logo: logo,
    };
  },
  components: {
  },
};
</script>

<style>
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 70px;
    padding: 0 54px;
    background-color: #fff;
  }
  .logo {
    width: 70px;
    height: 70px;
    border-radius: 50%;
  }
</style>