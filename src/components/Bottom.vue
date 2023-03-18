<template>
  <div class="bottom">
    <div class="bottom__item" v-for="item in items" :key="item.id">
      <img
        class="bottom__item-icon"
        :alt="item.iconAlt"
        :src="`./images/${item.icon}`"
      />
      <div class="bottom__item-describe">
        <div class="bottom__item-describe-number">{{ item.id }}</div>
        <div class="bottom__item-describe-title">{{ item.title }}</div>
        <div class="bottom__item-describe-body">{{ item.body }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'c-bottom',
  setup() {
    const items = [
      {
        id: '01',
        icon: 'image-retro-pcs.jpg',
        iconAlt: 'image retro pcs',
        title: 'Reviving Retro PCs',
        body: 'What happens when old PCs are given modern upgrades?',
      },
      {
        id: '02',
        icon: 'image-top-laptops.jpg',
        iconAlt: 'image top laptops',
        title: 'Top 10 Laptops of 2022',
        body: 'Our best picks for various needs and budgets.',
      },
      {
        id: '03',
        icon: 'image-gaming-growth.jpg',
        iconAlt: 'image gaming growth',
        title: 'The Growth of Gaming',
        body: 'How the pandemic has sparked fresh opportunities.',
      },
    ];

    return { items };
  },
};
</script>

<style lang="scss" scoped>
.bottom {
  display: grid;
  grid-template-rows: 1fr;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  margin-top: 40px;

  &__item {
    display: flex;

    &-icon {
      height: 120px;
      margin-right: 20px;
    }

    &-describe {
      &-number {
        margin-bottom: 10px;
        color: var(--color-grayish-blue);
        font-size: 2rem;
        font-weight: var(--font-bold);
      }

      &-title {
        margin-bottom: 10px;
        color: var(--color-very-dark-blue);
        font-size: 1.1rem;
        font-weight: var(--font-ex-bold);
        transition: color var(--transition-delay);

        &:hover {
          color: var(--color-soft-orange);
          cursor: pointer;
        }
      }

      &-body {
        line-height: 22px;
      }
    }
  }
}

@media (max-width: 550px) {
  .bottom {
    grid-template-rows: repeat(3, 1fr);
    grid-template-columns: 1fr;
    margin-top: 20px;
  }
}
</style>
