<template>
  <div class="aside">
    <div class="aside__title">new</div>
    <div class="aside__body" v-for="item in items" :key="item.title">
      <div class="aside__body-title">{{ item.title }}</div>
      <div class="aside__body-body">{{ item.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'c-aside',
  setup() {
    const items = [
      {
        title: 'Hydrogen VS Electric Cars',
        body: 'Will hydrogen-fueled cars ever catch up to EVs?',
      },
      {
        title: 'The Downsides of AI Artistry',
        body: 'What are the possible adverse effects of on-demand AI image generation?',
      },
      {
        title: 'Is VC Funding Drying Up?',
        body: 'Private funding by VC firms is down 50% YOY. We take a look at what that means.',
      },
    ];

    return { items };
  },
};
</script>

<style lang="scss" scoped>
.aside {
  background: var(--color-very-dark-blue);
  &__title {
    color: var(--color-soft-orange);
  }
  
  &__body {
    &-title {
    }
    &-body {
    }
  }
}
</style>
