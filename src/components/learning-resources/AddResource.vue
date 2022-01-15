<template>
  <base-card>
    <form @submit.prevent="submitData">
      <p class="form-control">
        <label for="title">Resource Title</label>
        <input type="text" name="title" id="title" ref="titleInput" />
      </p>
      <p class="form-control">
        <label for="description">Description</label>
        <textarea
          name="description"
          id="description"
          rows="3"
          ref="descriptionInput"
        ></textarea>
      </p>
      <p class="form-control">
        <label for="link">Resource Link</label>
        <input type="url" name="link" id="link" ref="linkInput" />
      </p>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addNewResource'],
  methods: {
    submitData() {
      const { titleInput, descriptionInput, linkInput } = this.$refs;
      this.addNewResource(
        titleInput.value,
        descriptionInput.value,
        linkInput.value
      );
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>