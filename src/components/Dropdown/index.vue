<template>
  <div class="dropdown">
    <nav class="dropdown__menu">
      <a class="dropdown__item" href="#">
        <user-icon size="16" class="dropdown__icon"></user-icon>
        Profile
      </a>
      <a class="dropdown__item" href="#">
        <bookmark-icon size="16" class="dropdown__icon"></bookmark-icon>
        Saved
      </a>
      <a class="dropdown__item" href="#">
        <settings-icon size="16" class="dropdown__icon"></settings-icon>
        Settings
      </a>
    </nav>
    <div class="dropdown__footer">
      <a href="#">Log Out</a>
    </div>
  </div>
</template>

<script>
import { UserIcon, BookmarkIcon, SettingsIcon } from 'vue-feather-icons';

export default {
  name: 'dropdown',
  components: {
    UserIcon,
    BookmarkIcon,
    SettingsIcon
  }
};
</script>

<style lang="scss" scoped>
.dropdown {
  position: absolute;
  z-index: 3;
  top: 5.4rem;
  right: 21rem;

  width: 20rem;
  background: #fff;
  box-shadow: var(--shadow);
  border-radius: 0.6rem;

  a {
    display: block;
    font-size: 1.4rem;
    color: var(--color-regular);
    padding: 0.8rem 1.6rem;

    &:hover {
      background-color: var(--color-background);
    }
  }

  &__menu {
    display: flex;
    flex-direction: column;
  }

  &__item {
    font-size: 1.4rem;
    color: var(--color-regular);
    padding: 0.8rem 1.6rem;

    display: flex;
    align-items: center;
  }

  &__icon {
    margin-right: 1rem;
  }

  &__footer {
    width: 100%;
    border-top: 1px solid var(--color-light);

    a {
      margin-left: 0.5rem;
    }
  }
}
</style>
