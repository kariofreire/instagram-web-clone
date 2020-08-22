<template>
  <main id="app">
    <topbar />
  </main>
</template>

<script>
import Topbar from '@/components/Topbar';

export default {
  name: 'App',
  components: { Topbar }
};
</script>

<style lang="scss">
@import '@/styles/global.scss';
</style>
