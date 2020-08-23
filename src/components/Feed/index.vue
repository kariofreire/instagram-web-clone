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
          post_image: 'rocketseat-post.png',
          comments: [
            {
              author: 'mayk',
              content: 'fala deeeev 🚀'
            },
            {
              author: 'guilhermerodz',
              content: 'belo wallpaper 💻'
            }
          ]
        },
        {
          username: 'traversymedia',
          profile_image: 'traversy.jpg',
          post_image: 'traversy-post.jpg',
          comments: [
            {
              author: 'deved',
              content: 'awesome 💚'
            },
            {
              author: 'tylerpotts',
              content: 'Amazing crash course 👏'
            }
          ]
        },
        {
          username: 'filipedeschamps',
          profile_image: 'filipe.jpg',
          post_image: 'filipe-post.jpg',
          comments: [
            {
              author: 'diego3g',
              content: 'muito booom 🚀'
            },
            {
              author: 'mayk',
              content: 'boa filipe 😜'
            }
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped></style>
