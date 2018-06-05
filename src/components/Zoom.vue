<template>
    <div id="zoom-main">
        <div id="poke-zoom-main"
        @click="$emit('onZoom')"
        >
            <div id="container-zoom"
                :style="{ backgroundColor: poke.color_1 }"
            >
                <h1>{{ poke.pokemon }}</h1>
                <img :src="poke.url_image">
                <div id="stats">
                    <span><strong>Type:</strong> {{ poke.type_1 }}</span>
                    <span><strong>Height:</strong> {{ poke.height }}</span>
                    <span><strong>Weight:</strong> {{ poke.weight }}</span>
                    <span><strong>Shape:</strong> {{ poke.shape }}</span>
                    <span><strong>Attack:</strong> {{ poke.attack }}</span>
                    <span><strong>Defense:</strong> {{ poke.defense }}</span>
                    <span><strong>HP:</strong> {{ poke.hp }}</span>
                    <span><strong>Speed:</strong> {{ poke.speed }}</span>
                    <span><strong>Ability 1:</strong> {{ poke.ability_1 }}</span>
                    <span><strong>Ability 2:</strong> {{ poke.ability_2 }}</span>
                    <span><strong>Hidden Ability:</strong> {{ poke.ability_hidden }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['poke']
}
</script>

<style scoped>

#poke-zoom-main {
    display: inline-block;
    padding-top: 33px;
    background: rgba(0, 0, 0, .69);
    width: 100%;
    height: 100%;
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
    color: white;
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
