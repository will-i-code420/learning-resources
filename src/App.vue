<template>
  <saved-resources></saved-resources>
</template>

<script>
import SavedResources from './components/learning-resources/SavedResources.vue';

export default {
  components: {
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