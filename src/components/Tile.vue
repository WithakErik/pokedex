<template>
  <div class="tile-group">
    <ul>
      <li>
        <div class="tile" :class="pokemon.type_1">
          <img :src="pokemon.url_image" style="width:150px">
           <div class="container">  
        <h3>{{ pokemon.pokemon }}</h3>
        <p><strong>Primary Type: </strong>{{ pokemon.type_1 }}</p>
        <p><strong>Secondary Type: </strong>{{ pokemon.type_2 }}</p>
        <p><strong>Speed: </strong>{{ pokemon.speed }}</p>
        <p><strong>Attack: </strong>{{ pokemon.attack }}</p>
        <p><strong>Defense: </strong>{{ pokemon.defense }}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['pokemon']
};
</script>

<style>

.tile-group {
  display: inline-block;
}

ul {
  list-style-type: none;
  display: flex;
}
p {
  line-height: 10px;
}
/* card styling credit to  https://www.w3schools.com/howto/howto_css_cards.asp */
.tile {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  margin: 10px;
  background-color: lightgrey;
  width: 250px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}
.tile:hover {
  box-shadow: 0 80px 400px 0 rgba(0,0,0,0.2);
}
.container {
  padding: 2px 16px;
}

.bug {
  background-color: #DAD690; 
}

.dark {
  background-color: #CA90DA; 
}

.dragon {
  background-color: #EECDE6
; 
}
.electric {
  background-color: #E2ABE3; 
}
.fairy {
  background-color: #CDEECE; 
}
.fighting {
  background-color: #B6E7C0; 
}
.fire {
  background-color: #DD98B7; 
}
.flying {
  background-color: #FAF0F9; 
}
.ghost {
  background-color: #E1D5F1; 
}
.grass {
  background-color: #B8C85B; 
}
.ground {
  background-color: #CDC56A; 
}
.ice {
  background-color: #CDDEEE;
 
}
.normal {
  background-color: #90DAB5; 
}
.poison {
  background-color:#D788B0; 
}
.psychic {
  background-color: #C9EDDD; 
}
.rock {
  background-color: #BED0E9; 
}
.steel {
  background-color: #A7B4E2; 
}
.water {
  background-color: #8890D7; 
}


</style>