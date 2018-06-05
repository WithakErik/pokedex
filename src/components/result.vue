<template>
<div id="tiles-main">
    <div class="pokes"
        :style="{ backgroundColor: item.color_1 }"
        >
        <h2>{{ item.pokemon }}</h2>
        <img :src="item.url_image">
        <ul>
            <li>Type: {{ item.type_1 }}</li>
            <li>Attack: {{ item.attack }}</li>
            <li>Defense: {{ item.defense }}</li>
        </ul>
    </div>
</div>
</template>

<script>
export default {
    props: ['item']
}
</script>

<style scpoed>
#tiles-main {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
}

.pokes {
    width: auto;
    padding: 6px;
    margin: 0;
    border-top: 2px solid gray;
    border-right: 2px solid black;
    border-bottom: 2px solid black;
    border-left: 2px solid gray;
    cursor: pointer;
    background-image: url('../assets/tile.png');
}

.pokes:hover {
    filter: saturate(3);
}

ul {
    padding: 0;
}

li {
    text-align: center;
    list-style: none;
    display: flex;
    flex-direction: row;
    justify-content: center;
}

img {
    height: 69px;
    width: 69px;
}
</style>
