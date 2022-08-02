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

  async created() {
    this.pets = await this.fetchPets();
  },

  methods: {
    async removePet(id) {
      if (confirm("Are you sure ?")) {
        const res = await fetch(
          `https://62e90083249bb1284eb837a8.mockapi.io/pets/${id}`,
          {
            method: "DELETE",
          }
        );

        res.status == 200
          ? (this.pets = this.pets.filter((pet) => pet.id !== id))
          : alert("An error occured");
      }
    },

    // removePet(id) {
    //   if (confirm("You sure?")) {
    //     this.pets = this.pets.filter((pet) => pet.id !== id);
    //   }
    // },

    addFavPet(id) {
      this.pets = this.pets.map((pet) =>
        pet.id === id ? { ...pet, isFavorite: !pet.isFavorite } : pet
      );
    },

    // addNewerPet(arrayProp) {
    //   this.pets.push(arrayProp);
    // },

    async fetchPets() {
      const res = await fetch(
        "https://62e90083249bb1284eb837a8.mockapi.io/pets"
      );
      const data = await res.json();
      return data;
    },

    async fetchPet(id) {
      const res = await fetch(
        `https://62e90083249bb1284eb837a8.mockapi.io/pets/${id}`
      );
      const data = await res.json();
      return data;
    },

    async addNewerPet(pet) {
      const res = await fetch(
        "https://62e90083249bb1284eb837a8.mockapi.io/pets",
        {
          method: "POST",
          headers: {
            "Content-type": "application/json",
          },
          body: JSON.stringify(pet),
        }
      );

      const data = await res.json();
      this.pets = [...this.pets, data];
    },
  },

  data() {
    return {
      pets: [],
    };
  },
};
</script>
