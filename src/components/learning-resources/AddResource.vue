<template>
  <base-dialog
    v-if="invalidInput"
    title="Invalid Input"
    @close-dialog="confirmError"
  >
    <template #default>
      <p>Invalid Input, make sure all inputs are complete and not blank</p>
    </template>
    <template #actions>
      <base-button @click="confirmError">Okay</base-button>
    </template>
  </base-dialog>
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
import BaseButton from '../UI/BaseButton.vue';
export default {
  components: { BaseButton },
  inject: ['addNewResource'],
  data() {
    return {
      invalidInput: false,
    };
  },
  methods: {
    submitData() {
      const titleInput = this.$refs.titleInput.value;
      const descriptionInput = this.$refs.descriptionInput.value;
      const linkInput = this.$refs.linkInput.value;
      if (
        !this.checkData(titleInput) ||
        !this.checkData(descriptionInput) ||
        !this.checkData(linkInput)
      ) {
        this.invalidInput = true;
        return;
      }
      this.addNewResource(titleInput, descriptionInput, linkInput);
    },
    checkData(data) {
      if (data.trim() !== '') return true;
      return false;
    },
    confirmError() {
      this.invalidInput = false;
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