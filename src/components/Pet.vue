<template>
  <div>
    <Card style="width: 25em">
      <template #header>
        <img
          src="https://www.primefaces.org/wp-content/uploads/2020/02/primefacesorg-primevue-2020.png"
          style="height: 15rem"
        />
      </template>
      <template #title>
        {{ pet.name }}
      </template>
      <template #subtitle> Age: {{ pet.age }} </template>
      <template #content>
        <p></p>
      </template>
      <template #footer>
        <Button
          @click="removeFn(pet.id)"
          icon="pi pi-times"
          label="Remove"
          class="p-button-danger"
          style="margin-left: 0.5em"
        />
        <Button
          @click="$emit('addFavPet', pet.id)"
          icon="pi pi-heart"
          :class="[
            pet.isFavorite ? '' : 'p-button-outlined',
            'p-button-rounded',
            'p-button-danger',
          ]"
          style="margin-left: 4rem"
        />
      </template>
    </Card>
  </div>
</template>

<script>
export default {
  props: {
    pet: Object,
  },

  methods: {
    removeFn(id) {
      console.log("clicked", id);
      this.$emit("EmitRemovePet", id);
    },
  },
};
</script>

<style>
</style>
