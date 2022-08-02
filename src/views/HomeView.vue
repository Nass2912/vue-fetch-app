<template>
  <Form @addNewPet="addNewerPet" />
  <Pets @EmitRemovePet="removePet" @favPet="addFavPet" :pets="pets" />
</template>

<script>
import Pets from "../components/Pets.vue";
import Form from "../components/Form.vue";

export default {
  name: "HomeView",
  components: { Pets, Form },
  data() {
    return {
      pets: [
        {
          id: 1,
          name: "Ruby",
          age: 2,
          img: "https://dog.ceo/api/breeds/image/random",
          isFavorite: true,
        },
        {
          id: 2,
          name: "Geo",
          age: 2,
          img: "https://dog.ceo/api/breeds/image/random",
          isFavorite: false,
        },
      ],
    };
  },

  methods: {
    removePet(id) {
      if (confirm("You sure?")) {
        this.pets = this.pets.filter((pet) => pet.id !== id);
      }
    },

    addFavPet(id) {
      this.pets = this.pets.map((pet) =>
        pet.id === id ? { ...pet, isFavorite: !pet.isFavorite } : pet
      );
    },

    addNewerPet(arrayProp) {
      this.pets.push(arrayProp);
    },
  },
};
</script>
