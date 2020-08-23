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
      @click.prevent="toggleDropdown"
      id="profile"
      class="topbar__link"
      href="#"
    >
      <img src="@/assets/profile.jpg" alt="Perfil do usuário" />
      <dropdown v-show="active" />
    </a>
  </nav>
</template>

<script>
import { HomeIcon, SendIcon, CompassIcon, HeartIcon } from 'vue-feather-icons';
import Dropdown from '@/components/Dropdown';

export default {
  name: 'topbar-nav',
  components: {
    HomeIcon,
    SendIcon,
    CompassIcon,
    HeartIcon,
    Dropdown
  },
  data() {
    return {
      active: false
    };
  },
  methods: {
    toggleDropdown() {
      this.active = !this.active;
    }
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
  position: relative;

  img {
    height: 100%;
    width: 100%;
    border-radius: 50%;
    object-fit: cover;
  }
}
</style>
