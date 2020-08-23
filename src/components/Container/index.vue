<template>
  <div class="container">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'container'
};
</script>

<style lang="scss" scoped>
.container {
  max-width: var(--width);
  padding: 3rem 2rem 0;
  margin: 0 auto;

  /* grid */
  display: grid;
  grid-template-columns: 1fr 23rem;
  grid-gap: 3rem;
}
</style>
