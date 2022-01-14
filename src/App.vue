<template>
  <the-header title="Learning Resources"></the-header>
  <saved-resources></saved-resources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import SavedResources from './components/learning-resources/SavedResources.vue';

export default {
  components: {
    TheHeader,
    SavedResources,
  },
  data() {
    return {};
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