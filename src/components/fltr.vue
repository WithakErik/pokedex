<template>
    <div>
        Type:
        <select v-model="fltr.type">
            <option value="all">All</option>
            <option v-for="t in types" :key="t">
                {{ t }}
            </option>
        </select>

        Atk:
        <input v-model="fltr.atk" type="number">
        Def:
        <input v-model="fltr.def" type="number">
    </div>
</template>

<script>
export default {
    name: 'fltr',
    props: ['fltr', 'types']
}
</script>

<style>

</style>
