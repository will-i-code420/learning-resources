<template>
  <ul>
    <learning-resource
      v-for="resource in resources"
      :key="resource.id"
      :resource="resource"
    ></learning-resource>
  </ul>
</template>

<script>
import LearningResource from './components/learning-resources/LearningResource.vue';

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
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official Vue.js Documentation',
          link: 'https://v3.vuejs.org',
        },
      ],
    };
  },
};
</script>

<style>
</style>