<template>
  <div class="p-grid">
    <div class="p-col-12 p-md-6 p-lg-3" v-for="pet in pets" :key="pet.id">
      <!-- <h3>{{ pet.name }}</h3> -->
      <Pet
        @addFavPet="$emit('favPet', pet.id)"
        @EmitRemovePet="$emit('EmitRemovePet', pet.id)"
        :pet="pet"
      />
    </div>
  </div>
</template>

<script>
import Pet from "./Pet.vue";

export default {
  props: {
    pets: Array,
  },

  components: {
    Pet,
  },

  emits: ["EmitRemovePet", "favPet"],
};
</script>

<style scoped>
.p-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  margin: 1rem 2rem;
}
</style>