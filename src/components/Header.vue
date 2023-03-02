<template>
  <div class="header">
    <Logo />
    <img
      class="header__burger-icon"
      src="@/assets/icons/icon-menu.svg"
      alt="burger-menu"
    />
    <div class="header__links">
      <div class="header__links-item" v-for="item in items" :key="item">
        {{ item }}
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '@/components/Logo.vue';

export default {
  name: 'c-header',
  components: {
    Logo,
  },
  setup() {
    const items = ['home', 'new', 'popular', 'trending', 'categories'];

    return { items };
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

  &__links {
    display: flex;

    &-item {
      text-transform: capitalize;

      &:not(:last-child) {
        margin: 0 10px;
      }
    }
  }
}
</style>
