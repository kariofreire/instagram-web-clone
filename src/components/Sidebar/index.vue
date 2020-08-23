<template>
  <div class="sidebar">
    <div class="sidebar__profile">
      <user-info
        image="profile.jpg"
        username="clodoaldodantas8"
        display_name="Clodoaldo Dantas"
      />
    </div>
    <div class="suggestions">
      <div class="suggestions__header">
        <h3>Sugestões para você</h3>
        <a href="#">ver tudo</a>
      </div>
      <ul class="suggestions__list">
        <li v-for="(user, index) in users" :key="index" class="suggestion">
          <user-info
            :image="user.image"
            :username="user.username"
            :display_name="user.display_name"
            :small="true"
          />
          <a class="primary" href="#">seguir</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import UserInfo from '@/components/UserInfo';

export default {
  name: 'sidebar',
  components: {
    UserInfo
  },
  data() {
    return {
      users: [
        {
          username: 'traversymedia',
          display_name: 'Traversy Media',
          image: 'traversy.jpg'
        },
        {
          username: 'rocketseat',
          display_name: 'Rocketseat',
          image: 'rocketseat.jpg'
        },
        {
          username: 'filipedeschamps',
          display_name: 'Filipe Deschamps',
          image: 'filipe.jpg'
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.sidebar {
  &__profile {
    margin-top: 1.8rem;
  }

  @media only screen and (max-width: 998px) {
    display: none;
  }
}

.suggestions {
  &__header {
    padding: 1.6rem 0 0.8rem;
    display: flex;
    align-items: center;
    justify-content: space-between;

    h3 {
      font-weight: bold;
      font-size: 1.4rem;
      color: var(--color-medium);
    }

    a {
      font-size: 1.4rem;
      color: var(--color-regular);
      font-weight: bold;
    }
  }
}

.suggestion {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.primary {
  font-size: 1.4rem;
  font-weight: bold;
  color: var(--color-primary);
}
</style>
