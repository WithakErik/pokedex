<template>
<div id="poke">
    <result
        v-for="item in list"
        :key="item.pokemon"
        :item="item"
    />
</div>
</template>

<script>
import result from './result.vue'
export default {
    props: ['list'],
    components: {
        result
    }
}
</script>

<style scoped>
</style>
