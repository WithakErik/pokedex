<template>
    <div id="header-main">
        <srt
            class="input"
            :srt="srt"
        />
        <fltr
            class="input"
            :fltr="fltr"
            :types="types"
        />
    </div>
</template>


<script>

// Imported components from the current folder
import srt from './srt'
import fltr from './fltr'

export default {
    // These are the arbitrary names we gave the components we imported on lines 2? & 2? (pokeFilter.vue & pokeSort.vue)
    components: {
        srt,
        fltr
    },
    // 'pokeList' was handed down from App.vue
    props: ['srt', 'fltr', 'types']
}
</script>

<style scoped>
.input {
    padding: 6px 0;
}
</style>
