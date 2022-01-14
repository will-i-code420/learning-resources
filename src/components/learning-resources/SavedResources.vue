<template>
  <ul>
    <learning-resource
      v-for="resource in resources"
      :key="resource.id"
      :resource="resource"
      @delete-resource="deleteResource"
    ></learning-resource>
  </ul>
</template>

<script>
import LearningResource from './LearningResource.vue';

export default {
  components: {
    LearningResource,
  },
  data() {
    return {
      resources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official Vue.js Documentation',
          link: 'https://v3.vuejs.org',
        },
        {
          id: 'vue-eslint-guide',
          title: 'Vue.js ESlint Guide',
          description: 'Official docs to use vue version of eslint',
          link: 'https://eslint.vuejs.org',
        },
      ],
    };
  },
  methods: {
    deleteResource(id) {
      this.resources = this.resources.filter((res) => res.id !== id);
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>