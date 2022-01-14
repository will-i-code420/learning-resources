<template>
  <li>
    <div>
      <header>
        <h2>{{ resource.title }}</h2>
        <button @click="deleteResource(resource.id)">Delete</button>
      </header>
    </div>
    <p>{{ resource.description }}</p>
    <nav>
      <a :href="resource.link" target="_blank">Learn More</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: {
    resource: {
      type: Object,
      required: true,
    },
  },
  methods: {
    deleteResource(id) {
      this.$emit('delete-resource', id);
    },
  },
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h2 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>