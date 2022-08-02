<template>
  <form @submit="onSubmit" class="p-formgroup-inline">
    <div class="p-field">
      <label for="name" class="p-sr-only">name</label>
      <InputText v-model="name" id="name" type="text" placeholder="name" />
    </div>
    <div class="p-field">
      <label for="age" class="p-sr-only">age</label>
      <InputText v-model="age" id="age" type="text" placeholder="age" />
    </div>
    <div class="p-field">
      <label for="url" class="p-sr-only">url</label>
      <InputText v-model="url" id="url" type="text" placeholder="url" />
    </div>
    <Button type="submit" label="Save" />
  </form>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      name: "",
      age: "",
      url: "",
      isFavorite: false,
    };
  },

  methods: {
    onSubmit(e) {
      e.preventDefault();

      const newPet = {
        id: Math.random(),
        name: this.name,
        age: this.age,
        url: this.url,
      };

      this.$emit("addNewPet", newPet);
    },
  },
};
</script>

<style scoped>
.p-formgroup-inline {
  display: inline-flex;
  gap: 2rem;
  margin-top: 2rem;
}
</style>