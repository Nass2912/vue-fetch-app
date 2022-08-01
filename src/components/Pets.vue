<template>
    <div class="pets">
        <div v-for="pet in pets" :key="pet.id">
            <!-- <h3>{{ pet.name }}</h3> -->
            <Pet :pet="pet" />
        </div>
    </div>
</template>

<script>
import Pet from "./Pet.vue"

export default {
    props: {
        pets: Array
    },

    components: {
        Pet
    }
}
</script>