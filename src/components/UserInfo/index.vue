<template>
  <div class="user-info">
    <img
      class="user-info__image"
      :class="{ small: small }"
      :src="resolveImage"
      alt="Perfil do usuário"
    />
    <div class="user-info__content">
      <strong>{{ username }}</strong>
      <span v-if="display_name">{{ display_name }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'user-info',
  props: {
    username: String,
    display_name: String,
    image: String,
    small: Boolean
  },
  computed: {
    resolveImage() {
      return require(`@/assets/${this.image}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.user-info {
  display: flex;
  align-items: center;
  margin: 0.8rem 0;

  &__image {
    height: 5.6rem;
    width: 5.6rem;
    border-radius: 50%;
    margin-right: 2rem;

    &.small {
      height: 3.2rem;
      width: 3.2rem;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;

    span {
      font-size: 1.2rem;
      color: var(--color-medium);
    }
  }
}
</style>
