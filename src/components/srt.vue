<template>
    <div>
        Sort:
        <select v-model="srt.property">
            <option value="pokemon">Name</option>
            <option value="type_1">Type</option>
            <option value="shape">Shape</option>
            <option value="attack">Atk</option>
            <option value="defense">Def</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'srt',
    props: ['srt']
}
</script>

<style>

</style>
