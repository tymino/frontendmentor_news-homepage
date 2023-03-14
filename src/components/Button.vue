<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'c-button',
};
</script>

<style lang="scss" scoped>
.button {
  padding: 12px 22px;
  
  background: var(--color-soft-red);
  border: none;

  color: var(--color-off-white);
  font-weight: var(--font-bold);
  letter-spacing: 2px;
  text-transform: uppercase;

  transition: background-color var(--transition-delay);

  &:hover {
    background: var(--color-very-dark-blue);
  }
}
</style>