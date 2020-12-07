<template>
  <div id="app">
    <draggable v-model="list" @update="onCheck">
      <transition-group tag="div" class="grid" name="grid">
        <div v-for="item in list" :key="item" class="cell">
          <img :src="item" alt="alt" class="image" />
        </div>
      </transition-group>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  name: 'App',
  components: {
    draggable,
  },
  methods: {
    onCheck(event) {
      console.log('event', event)
    },
  },
  data() {
    return {
      list: [
        'https://4.bp.blogspot.com/-URHCBjlunBE/V_sZsJ2N7kI/AAAAAAAAEYo/upJHZ5ZzVz4O_l6dqtNpNne_13KSiI_RwCEw/s1600/2-76c21c606beb5faa41286c5371233603.jpg',
        'http://i.ebayimg.com/images/i/111648957592-0-1/s-l1000.jpg',
        'https://cdn11.bigcommerce.com/s-0kvv9/images/stencil/1280x1280/products/15869/79196/yugioh-dragons-of-legend-single-card-super-rare-drlg-en043-number-c5-chaos-chimera-dragon-23__40220.1461152608.jpg',
        'https://i.pinimg.com/736x/89/c8/50/89c8506a214145bf63d6f04c2b9ff194--yu-gi-oh-gunnar.jpg',
        'https://ms.yugipedia.com//thumb/4/4f/CardDestruction-OP09-EN-SR-UE.png/300px-CardDestruction-OP09-EN-SR-UE.png',
        'https://steemitimages.com/DQmRjYD3LGUo1QV5JWPDUGGt5UMRDkajFqBzT6QSf7cy4A8/y1.jpg',
        'https://ms.yugipedia.com//a/a6/CardShuffle-DR1-EN-C-UE.png',
        'https://www.pojo.com/wp-content/uploads/2018/03/kingofd.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/12/PSV-EN000-jinzo.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/12/Law-of-the-Cosmos.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/12/Psychic-Megacyber.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Psychic-Bounder.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Meklord-Astro-Dragon-Triskelion.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Meklord-Emperor-Wisel-Synchro-Absorption.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Meklord-Emperor-Wisel.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Meklord-Nucleus-Infinity-Core.jpg',
        'https://www.pojo.com/wp-content/uploads/2020/11/Meklord-Assembly.jpg',
      ],
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.grid {
  display: grid;
  grid-template-columns: repeat(6, 300px);
  grid-template-rows: repeat(3, 300px);
  grid-gap: 0.2em;
}

.grid-move {
  transition: all 0.5s;
}

.cell {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image {
  cursor: move;
  width: 200px;
  height: 250px;
}
</style>
