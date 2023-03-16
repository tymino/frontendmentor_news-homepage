<template>
  <div class="content">
    <Header />
    <div class="content__body">
      <Main class="content__body-main" />
    </div>
    <div class="content__aside"></div>
    <div class="content__bottom"></div>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
}

.content {
  margin-top: 40px;
  width: 100%;
  max-width: 1112px;
}

@media (max-width: 640px) {
}
</style>
