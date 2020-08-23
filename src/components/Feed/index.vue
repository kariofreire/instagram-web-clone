<template>
  <div class="feed">
    <ul class="feed_posts">
      <post v-for="(post, index) in posts" :key="index" :post="post" />
    </ul>
  </div>
</template>

<script>
import Post from './Post';

export default {
  name: 'feed',
  components: {
    Post
  },
  data() {
    return {
      posts: [
        {
          username: 'rocketseat',
          profile_image: 'rocketseat.jpg',
          post_image: 'rocketseat-post.png'
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped></style>
