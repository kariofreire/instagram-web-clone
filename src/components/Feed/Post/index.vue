<template>
  <li class="post">
    <div class="post__header">
      <user-info
        :image="post.profile_image"
        :username="post.username"
        :small="true"
      />
      <button @click="$emit('show-modal')" class="post__menu">
        <more-horizontal-icon size="22"></more-horizontal-icon>
      </button>
    </div>
    <div class="post__thumbnail">
      <img :src="resolveImage" alt="Postagem do usuário" />
    </div>
    <div class="post__actions">
      <heart-icon size="24"></heart-icon>
      <message-circle-icon size="24"></message-circle-icon>
      <send-icon size="24"></send-icon>
      <bookmark-icon size="24"></bookmark-icon>
    </div>
    <ul class="post__comments">
      <li v-for="(comment, index) in post.comments" :key="index">
        <strong>{{ comment.author }}</strong>
        <span>{{ comment.content }}</span>
      </li>
    </ul>
    <div class="post__form">
      <input v-model="text" type="text" placeholder="Adicione um comentário" />
      <button :disabled="!text">Publicar</button>
    </div>
  </li>
</template>

<script>
import UserInfo from '@/components/UserInfo';

import {
  MoreHorizontalIcon,
  HeartIcon,
  MessageCircleIcon,
  SendIcon,
  BookmarkIcon
} from 'vue-feather-icons';

export default {
  name: 'post',
  components: {
    UserInfo,
    MoreHorizontalIcon,
    HeartIcon,
    MessageCircleIcon,
    SendIcon,
    BookmarkIcon
  },
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      text: ''
    };
  },
  computed: {
    resolveImage() {
      return require(`@/assets/${this.post.post_image}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.post {
  border: 1px solid var(--color-light);
  background-color: #fff;
  margin-bottom: 6rem;

  &__header {
    padding: 0.8rem 1.6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__menu {
    background-color: transparent;
    border: 0;
    outline: 0;
    cursor: pointer;
  }

  &__thumbnail img {
    display: block;
    width: 100%;
  }

  &__actions {
    margin: 1rem 0;
    padding: 0 1.6rem;
    display: flex;
    align-items: center;

    svg {
      margin: 0 0.5rem;

      &:last-child {
        margin-left: auto;
      }
    }
  }

  &__comments {
    padding: 1rem 1.6rem;

    strong {
      margin-right: 0.5rem;
    }
  }

  &__form {
    border-top: 1px solid var(--color-light);
    padding: 1.6rem;
    display: flex;

    input {
      flex: 1;
      border: none;
      outline: 0;
    }

    button {
      background: transparent;
      border: none;
      outline: 0;
      cursor: pointer;
      font-size: 1.4rem;
      font-weight: bold;
      color: var(--color-primary);

      &:disabled {
        opacity: 0.5;
      }
    }
  }
}
</style>
