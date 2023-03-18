<template>
  <div class="main">
    <picture class="main__picture">
      <source
        srcset="@/assets/images/image-web-3-mobile.jpg"
        media="(max-width: 720px)"
      />
      <img src="@/assets/images/image-web-3-desktop.jpg" alt="web-3" />
    </picture>

    <div class="main__wrapper">
      <div class="main__title">The Bright Future of Web 3.0?</div>
      <div class="main__describe">
        <div class="main__describe-text">
          We dive into the next evolution of the web that claims to put the
          power of the platforms back into the hands of the people. But is it
          really fulfilling its promise?
        </div>

        <Button class="main__describe-button">read more</Button>
      </div>
    </div>
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
.main {
  display: flex;
  flex-direction: column;

  &__picture {
    & > img {
      width: 100%;
      height: auto;
      display: block;
    }
  }

  &__wrapper {
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 20px;
    margin-top: 20px;
  }

  &__title {
    padding-right: 20px;
    color: var(--color-very-dark-blue);
    font-size: 3.3rem;
    font-weight: var(--font-ex-bold);
    line-height: 3.3rem;
  }

  &__describe {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    padding-right: 10px;
  }
}

@media (max-width: 550px) {
  .main {
    margin-bottom: 20px;

    &__wrapper {
      grid-template-rows: repeat(2, 1fr);
      grid-template-columns: 1fr;
    }

    &__title {
      font-size: 3rem;
    }

    &__describe {
      padding-right: 0px;

      &-button {
        margin-top: 20px;
      }
    }
  }
}
</style>
