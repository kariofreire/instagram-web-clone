<template>
  <nav class="topbar__menu">
    <a class="topbar__link centralize" href="#">
      <home-icon class="topbar__icon" size="22"></home-icon>
    </a>
    <a class="topbar__link centralize" href="#">
      <send-icon class="topbar__icon" size="22"></send-icon>
    </a>
    <a class="topbar__link centralize" href="#">
      <compass-icon class="topbar__icon" size="22"></compass-icon>
    </a>
    <a class="topbar__link centralize" href="#">
      <heart-icon class="topbar__icon" size="22"></heart-icon>
    </a>
    <a
      @click.prevent="$emit('show')"
      id="profile"
      class="topbar__link"
      href="#"
    >
      <img src="@/assets/person-1.svg" alt="Perfil do usuário" />
    </a>
  </nav>
</template>

<script>
import { HomeIcon, SendIcon, CompassIcon, HeartIcon } from 'vue-feather-icons';

export default {
  name: 'topbar-nav',
  components: {
    HomeIcon,
    SendIcon,
    CompassIcon,
    HeartIcon
  }
};
</script>

<style lang="scss" scoped>
.topbar {
  &__menu {
    display: flex;
    align-items: center;
  }

  &__link:not(:first-child) {
    margin-left: 2.2rem;
  }

  &__icon {
    color: var(--color-regular);
  }
}

#profile {
  width: 2.2rem;
  height: 2.2rem;

  img {
    height: 100%;
    width: 100%;
    border-radius: 50%;
  }
}
</style>
