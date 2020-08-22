<template>
  <header class="topbar">
    <div class="topbar__container centralize">
      <topbar-logo />
      <topbar-nav />
    </div>
  </header>
</template>

<script>
import TopbarLogo from './TopbarLogo';
import TopbarNav from './TopbarNav';

export default {
  name: 'topbar',
  components: {
    TopbarLogo,
    TopbarNav
  }
};
</script>

<style lang="scss" scoped>
.topbar {
  height: 5.4rem;
  background-color: #fff;
  border-bottom: 1px solid var(--color-light);

  &__container {
    height: 100%;
    max-width: 97.5rem;
    margin: 0 auto;
    padding: 0 2rem;
  }
}
</style>
