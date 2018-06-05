<template>
    <div id="zoom-main">
        <div id="poke-zoom-main"
        @click="onExit"
        >
            <div id="container-zoom"
                :style="{ backgroundColor: selected.color_1 }"
            >
                <h1>{{ selected.pokemon }}</h1>
                <img :src="selected.url_image">
                <div id="stats">
                    <span><strong>Type:</strong> {{ selected.type_1 }}</span>
                    <span><strong>Height:</strong> {{ selected.height }}</span>
                    <span><strong>Weight:</strong> {{ selected.weight }}</span>
                    <span><strong>Shape:</strong> {{ selected.shape }}</span>
                    <span><strong>Attack:</strong> {{ selected.attack }}</span>
                    <span><strong>Defense:</strong> {{ selected.defense }}</span>
                    <span><strong>HP:</strong> {{ selected.hp }}</span>
                    <span><strong>Speed:</strong> {{ selected.speed }}</span>
                    <span><strong>Ability 1:</strong> {{ selected.ability_1 }}</span>
                    <span><strong>Ability 2:</strong> {{ selected.ability_2 }}</span>
                    <span><strong>Hidden Ability:</strong> {{ selected.ability_hidden }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        selected: Object,
        onExit: {
            type: Function
        }
    }
}
</script>

<style scoped>

#poke-zoom-main {
    position: fixed;
    display: inline-block;
    padding-top: 33px;
    background: rgba(0, 0, 0, .69);
    width: 100%;
    height: 100%;
    z-index: 99;
}

#container-zoom {
    border-radius: 33px;
    display: flex;
    flex-direction: column;
    margin: auto;
    padding: 33px;
    display: flex;
    width: fit-content;
    align-content: center;
    justify-content: space-around;
    align-items: center;
}

h1 {
    font-size: 4rem;
    margin: auto;
}

img {
    height: auto;
    width: 200px;
}

#stats {
    display: flex;
    flex-direction: column;
}
</style>
