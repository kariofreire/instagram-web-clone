<template>
  <header class="topbar">
    <div class="topbar__container centralize">
      <topbar-logo />
      <topbar-nav @show="toggleDropdown" />
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
  position: sticky;
  top: 0px;
  z-index: 10;
  height: 5.4rem;
  background-color: #fff;
  border-bottom: 1px solid var(--color-light);

  &__container {
    height: 100%;
    max-width: var(--width);
    padding: 0 2rem;
    margin: 0 auto;
  }
}
</style>
