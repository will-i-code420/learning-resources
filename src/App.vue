<template>
  <the-header title="Learning Resources"></the-header>
  <the-resources></the-resources>>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/layouts/TheResources.vue';

export default {
  components: {
    TheHeader,
    TheResources,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html {
  font-family: 'Roboto', sans-serif;
}
</style>