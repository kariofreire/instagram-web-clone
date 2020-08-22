<template>
  <div class="stories">
    <ul class="stories__list">
      <li v-for="(storie, index) in stories" :key="index" class="storie">
        <img
          class="storie__image"
          :src="resolveImage(storie.image)"
          :alt="storie.name"
        />
        <span class="storie__name">
          {{ storie.name }}
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
import storiesData from '@/data/stories.json';

export default {
  name: 'stories',
  data() {
    return {
      stories: storiesData
    };
  },
  methods: {
    resolveImage(filename) {
      return require(`@/assets/${filename}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.stories {
  background-color: #fff;
  padding: 1.6rem 0;
  border: 1px solid var(--color-light);
  overflow-x: scroll;

  &__list {
    display: flex;
  }
}

.storie {
  flex: 0 0 8rem;
  margin: 0 0.5rem;
  text-align: center;
  cursor: pointer;

  &__image {
    height: 5.6rem;
    width: 5.6rem;
    border-radius: 50%;
    border: 3px solid #e1306c;
  }

  &__name {
    font-size: 1.4rem;
    margin-top: 0.2rem;
    display: block;
  }
}
</style>
