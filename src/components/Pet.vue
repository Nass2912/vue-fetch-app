<template>
    <div>
        <Card style="width: 25em">
            <template #header>
                <img src="https://www.primefaces.org/wp-content/uploads/2020/02/primefacesorg-primevue-2020.png"
                    style="height: 15rem" />
            </template>
            <template #title>
                {{ pet.name }}
            </template>
            <template #subtitle>
                Age: {{ pet.age }}
            </template>
            <template #content>
                <p></p>
            </template>
            <template #footer>
                <Button icon="pi pi-times" label="Cancel" class="p-button-secondary" style="margin-left: .5em" />
                <Button icon="pi pi-heart" class="p-button-rounded p-button-danger" style="margin-left: 4rem;" />

                <Button icon="pi pi-heart" class="p-button-rounded p-button-danger p-button-outlined" />
            </template>
        </Card>
    </div>
</template>

<script>
export default {
    props: {
        pet: Object
    }
}
</script>

<style>
</style>