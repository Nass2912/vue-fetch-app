<template>
    <div class="p-formgroup-inline">
        <div class="p-field">
            <label for="name" class="p-sr-only">name</label>
            <InputText id="name" type="text" placeholder="name" />
        </div>
        <div class="p-field">
            <label for="age" class="p-sr-only">age</label>
            <InputText id="age" type="text" placeholder="age" />
        </div>
        <div class="p-field">
            <label for="url" class="p-sr-only">url</label>
            <InputText id="url" type="text" placeholder="url" />
        </div>
        <Button type="button" label="Save" />
    </div>
</template>

<style scoped>
.p-formgroup-inline {
    display: inline-flex;
    gap: 2rem;
    margin-top: 2rem;
}
</style>