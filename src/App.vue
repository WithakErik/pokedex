<template>
  <div id="app">
    <zoom
      v-if="zoomed"
      :selected="selected"
      :onExit="onExit"
    />
    <!-- Main Pokedex thing -->
    <div id="app-container">
      <h1>Manipulate your poke search!</h1>
      <div id="app-main">

        <Header id="header"
          :types="types"
          :srt="srt"
          :fltr="fltr"
        />

        <Results id="results"
          v-if="list.length !== 0"
          :list="list"
          :onSelect="onSelect"
        />
        <div
          v-else
        >
          <h1>No Pokemons to sea hear</h1>
        </div>
      </div>
    </div>
</div>
</template>

<script>
import Header from './components/Header'
import Results from './components/Results'
import Zoom from './components/Zoom'
import pokemon from './assets/pokemon'

export default {
  name: 'app',
  
  data() {
    return {
      pokemon,
      srt: {
        property: 'pokemon',
        direction: 1
      },
      fltr: {
        type: 'all',
        atk: 0,
        def: 0
      },
      zoomed: false,
      selected: null
    };
  },
  // COMPONENTS
  components: {
    Header,
    Results,
    Zoom
  },
  // METHODS
  methods: {
    onSelect: function(selected) {
      this.zoomed = true;
      this.selected = selected;
    },
    onExit: function() {
      this.zoomed = false;
    },
    direction(direction) {
      this.srt.direction = direction;
    }
  },

  // COMPUTED
  computed: {
    types() {
      const type1 = this.pokemon.map(p => p.type_1);
      const type2 = this.pokemon.map(p => p.type_2);
      const set = new Set(type1.concat(type2));
      return [...set.values()];
    },
    list() {
      return this.filtered.slice().sort((a, b) => {
        const elementA = a[this.srt.property];
        const elementB = b[this.srt.property];
        if(elementA === elementB) return 0;
        if(elementA < elementB) return this.srt.direction;
        return -this.srt.direction;
      });
    },
    filtered() {
      const { type, atk, def } = this.fltr;
      return this.pokemon.slice().filter(a => {
        return (type === 'all'
        || a.type_1 === type)
        && (atk < 1 || a.attack >= atk)
        && (def < 1 || a.defense >= def);
      });
    }
  }
}
</script>

<style scoped>
#app {
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}

#app-container {
  display: flex;
  margin: auto;
  flex-direction: column;
  border-top: 3px solid gray;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
  border-left: 3px solid gray;
  background-color: slategrey;
  width: fit-content;
  background-image: url('assets/thread.png');
}

#app-main {
  display: flex;
  flex-direction: column;
  margin: auto;
  text-align: center;
  width: 600px;
}

h1 {
  text-align: center;
}

#results {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 13px;
  margin: 6px;
  height: 350px;
  overflow: auto;
  border-top: 3px solid black;
  border-right: 3px solid gray;
  border-bottom: 3px solid gray;
  border-left: 3px solid black;
  background-color: darkcyan;
  background-image: url('assets/paper.png');
}
</style>
