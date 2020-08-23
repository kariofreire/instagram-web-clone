<template>
  <div class="feed">
    <ul class="feed_posts">
      <post
        @show-modal="toggleModal"
        v-for="(post, index) in posts"
        :key="index"
        :post="post"
      />
    </ul>
    <modal @close-modal="toggleModal" v-show="show" />
  </div>
</template>

<script>
import Post from './Post';
import Modal from '@/components/Modal';

export default {
  name: 'feed',
  components: {
    Post,
    Modal
  },
  data() {
    return {
      show: false,
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
  },
  methods: {
    toggleModal() {
      this.show = !this.show;
    }
  }
};
</script>

<style lang="scss" scoped>
.feed {
  @media only screen and (max-width: 998px) {
    width: 80%;
    margin: auto;
  }

  @media only screen and (max-width: 800px) {
    width: 90%;
  }

  @media only screen and (max-width: 600px) {
    width: 100%;
  }
}
</style>
