<template>
  <li>
    <base-card>
      <header>
        <h2>{{ resource.title }}</h2>
        <base-button mode="flat" @click="deleteResource(resource.id)"
          >Delete</base-button
        >
      </header>
      <p>{{ resource.description }}</p>
      <nav>
        <a :href="resource.link" target="_blank">Learn More</a>
      </nav>
    </base-card>
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
  inject: ['deleteResource'],
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