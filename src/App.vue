<template>
  <main id="app">
    <topbar />
    <container>
      <feed />
      <sidebar />
    </container>
  </main>
</template>

<script>
import Topbar from '@/components/Topbar';
import Container from '@/components/Container';
import Feed from '@/components/Feed';
import Sidebar from '@/components/Sidebar';

export default {
  name: 'App',
  components: {
    Topbar,
    Container,
    Feed,
    Sidebar
  }
};
</script>

<style lang="scss">
@import '@/styles/global.scss';
</style>
