<template>
  <div>
    <draggable
      v-model="items"
      class="row"
      :sort="true"
      v-bind="dragOptions"
      @start="isDragging = true"
      @end="isDragging = false"
    >
      <transition-group type="transition" name="flip-list">
        <v-col v-for="image in items" :key="image" cols="4">
          <img :src="image" alt="" class="item" />
        </v-col>
      </transition-group>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  components: {
    draggable,
  },
  data() {
    return {
      isDragging: false,
      items: [
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
  computed: {
    dragOptions() {
      return {
        animation: 0,
        group: 'description',
        disabled: false,
        ghostClass: 'ghost',
      }
    },
  },
}
</script>

<style lang="css">
.item {
  margin-top: 10px;
  cursor: move;
  margin-left: 20px;
  width: 200px;
  height: 250px;
}

.flip-list-move {
  transition: transform 0.5s;
}
.no-move {
  transition: transform 0s;
}
</style>
