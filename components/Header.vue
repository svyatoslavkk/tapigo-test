<template>
  <header class="header">
    <div class="flex-content">
      <button class="icon-button search">
        <SearchIcon />
      </button>
      <button class="menu-button">
        <MenuIcon />
      </button>
      <button class="desktop-button">
        <span class="menu-icon">
          <MenuIcon />
        </span>
        <span class="text">Сервисы</span>
      </button>
    </div>
    <div>
      <img :src="logo" class="logo" />
    </div>
    <div class="flex-content">
      <button class="desktop-button">
        <span class="text">Разместить</span>
      </button>
      <button class="icon-button">
        <LogoutIcon />
      </button>
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
  .text {
    font-size: 16px;
    color: #fff;
    font-weight: 500;
  }
  .header {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 70px;
    padding: 0 16px;
    background-color: #fff;
    transition: 0.3s ease;
  }
  .logo {
    width: 70px;
    height: 70px;
    border-radius: 50%;
  }
  .flex-content {
    display: flex;
    align-items: center;
    gap: 24px;
  }
  .desktop-button {
    display: none;
    align-items: center;
    gap: 0.5rem;
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
    background-color: #1F3B8B;
    cursor: pointer;
    transition: 0.4s ease;
  }
  .desktop-button:hover {
    background-color: #212A4E;
  }
  .icon-button svg {
    stroke: #1F3B8B;
  }
  .icon-button svg:hover {
    stroke: #212A4E;
  }
  .button-icon svg,
  .menu-icon svg {
    stroke: #fff;
  }
  .menu-button {
    display: flex;
  }
  .menu-button svg {
    stroke: #1F3B8B;
  }
  .menu-button svg:hover {
    stroke: #212A4E;
  }
  .menu-button svg,
  .menu-icon svg {
    width: 36px;
    height: 36px;
  }
  .icon-button.search {
    display: none;
  }
  @media (min-width: 600px) {
    .menu-button {
      display: none;
    }
    .desktop-button {
      display: flex;
    }
    .menu-button svg,
    .menu-icon svg {
      width: 20px;
      height: 20px;
    }
    .icon-button.search {
      display: flex;
    }
  }
  @media (min-width: 1280px) {
    .header {
      padding: 0 54px;
    }
    .flex-content {
      display: flex;
      align-items: center;
      gap: 48px;
    }
  }
</style>