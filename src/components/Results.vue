<template>
<div id="poke">
    <result
        v-for="item in list"
        :key="item.pokemon"
        :item="item"
        :onSelect="onSelect"
    />
</div>
</template>

<script>
import result from './result.vue'
export default {
    props: {
        list: Array,
        onSelect: {
            type: Function
        }
    },
    components: {
        result
    }
}
</script>

<style scoped>
</style>
