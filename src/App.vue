<template>
  <div class="content">
    <div class="content__header">
      <Header />
    </div>
    <div class="content__main">
      <Main />
    </div>
    <div class="content__aside">
      <Aside />
    </div>
    <div class="content__bottom"></div>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import Aside from '@/components/Aside.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Aside,
  },
};
</script>

<style lang="scss" scoped>
.content {
  display: grid;
  grid-template-rows: repeat(4, auto);
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  grid-template-areas:
    'a a a'
    'b b c'
    'b b c'
    'd d d';
  margin-top: 40px;
  width: 100%;
  max-width: 1112px;

  &__header {
    grid-area: a;
    margin-bottom: 40px;
  }
  &__main {
    grid-area: b;
  }
  &__aside {
    grid-area: c;
  }
  &__bottom {
    grid-area: d;
  }
}

@media (max-width: 640px) {
}
</style>
