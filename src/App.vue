<template>
  <div class="content">
    <Header />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
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
</style>
