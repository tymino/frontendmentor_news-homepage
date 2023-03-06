<template>
  <div class="main">
    <picture class="main__picture">
      <source
        srcset="@/assets/images/image-web-3-mobile.jpg"
        media="(max-width: 720px)"
      />
      <img src="@/assets/images/image-web-3-desktop.jpg" alt="web-3" />
    </picture>

    <div class="main__title">The Bright Future of Web 3.0?</div>
    <div class="main__describe">
      We dive into the next evolution of the web that claims to put the power of
      the platforms back into the hands of the people. But is it really
      fulfilling its promise?
    </div>

    <Button class="main__button">read more</Button>
  </div>
</template>

<script>
import Button from '@/components/Button.vue';

export default {
  name: 'c-main',
  components: {
    Button,
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
    text-transform: capitalize;

    &-item {
      margin-left: 30px;
      transition: color var(--transition-delay);

      &:hover {
        color: var(--color-soft-red);
        cursor: pointer;
      }
    }
  }
}
</style>
