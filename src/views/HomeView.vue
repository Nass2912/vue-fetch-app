<template>
  <Pets :pets="pets" />
</template>

<script>
import Pets from "../components/Pets.vue";

export default {
  name: "HomeView",
  components: { Pets },
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
};
</script>
