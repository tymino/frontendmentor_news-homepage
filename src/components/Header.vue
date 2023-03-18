<template>
  <div class="header">
    <Logo />
    <img
      class="header__burger-icon"
      src="@/assets/icons/icon-menu.svg"
      alt="burger-menu"
      @click="openMenu"
    />
    <div
      class="header__links"
      :class="{ 'header__links--active': isActiveMenu }"
    >
      <img
        class="header__close-icon"
        src="@/assets/icons/icon-menu-close.svg"
        alt="menu-close"
        @click="closeMenu"
      />

      <div class="header__links-item" v-for="item in items" :key="item">
        {{ item }}
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

import Logo from '@/components/Logo.vue';

export default {
  name: 'c-header',
  components: {
    Logo,
  },
  setup() {
    const items = ['home', 'new', 'popular', 'trending', 'categories'];
    let isActiveMenu = ref(false);

    const openMenu = () => {
      isActiveMenu.value = true;
    };
    const closeMenu = () => {
      isActiveMenu.value = false;
    };

    return { items, isActiveMenu, openMenu, closeMenu };
  },
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__burger-icon {
    display: none;
  }

  &__close-icon {
    display: none;
  }

  &__links {
    display: flex;

    &-item {
      margin-left: 30px;
      text-transform: capitalize;
      transition: color var(--transition-delay);

      &:hover {
        color: var(--color-soft-red);
        cursor: pointer;
      }
    }
  }
}

@media (max-width: 550px) {
  @keyframes menuOpen {
    0% {
      right: -100%;
      opacity: 0;
    }
    50% {
      opacity: 0;
    }
    100% {
      right: 0%;
      opacity: 1;
    }
  }
  @keyframes menuClose {
    0% {
      right: 0%;
      opacity: 1;
    }
    50% {
      opacity: 0;
    }

    100% {
      right: -100%;
    }
  }

  .header {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;

    &__burger-icon {
      display: block;
    }
    &__close-icon {
      display: block;
      align-self: flex-end;
      width: 32px;
      height: 32px;
      margin-bottom: 60px;
    }

    &__links {
      position: fixed;
      top: 0;
      right: -100%;
      width: 70%;
      height: 100vh;

      display: flex;
      flex-direction: column;
      padding: 30px 20px 0px 30px;

      background: var(--color-off-white);

      animation-name: menuClose;
      animation-duration: 0.3s;

      &--active {
        animation-name: menuOpen;
        animation-duration: 0.3s;
        right: 0%;
      }

      &-item {
        margin: 12px 0px;
        color: var(--color-very-dark-blue);
        font-size: 1.3rem;
      }
    }
  }
}
</style>
