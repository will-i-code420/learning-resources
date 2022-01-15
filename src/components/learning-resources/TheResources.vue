<template>
  <base-card>
    <base-button @click="setSelectedTab('saved-resources')" :mode="savedBtnMode"
      >Stored Resources</base-button
    >
    <base-button @click="setSelectedTab('add-resource')" :mode="addBtnMode"
      >Add Resource</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import SavedResources from './SavedResources.vue';
import AddResource from './AddResource.vue';

export default {
  components: {
    SavedResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: 'saved-resources',
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
  computed: {
    savedBtnMode() {
      return this.selectedTab === 'saved-resources' ? null : 'flat';
    },
    addBtnMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
  },
  provide() {
    return {
      resources: this.resources,
      addNewResource: this.addNewResource,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addNewResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString(),
        title,
        description,
        link,
      };
      this.resources.push(newResource);
      this.selectedTab = 'saved-resources';
    },
  },
};
</script>

<style scoped>
</style>