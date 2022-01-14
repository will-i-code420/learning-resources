<template>
  <li>
    <div>
      <header>
        <h2>{{ resource.title }}</h2>
        <button>Delete</button>
      </header>
    </div>
    <p>{{ resource.description }}</p>
    <nav>
      <a :href="resource.link">Learn More</a>
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
};
</script>