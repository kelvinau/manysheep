<template>
  <div class="background">
    <div class="clear-btn-container">
      Sheep Spawned: {{sheep.length}}/{{MAX_NUM_OF_SHEEP}}
      <button
        @click="addSheep"
         :disabled="sheep.length >= MAX_NUM_OF_SHEEP">Add Sheep</button>
      <button
        @click="clearAllSheep">Kill Them All 😆</button>
    </div>
    <floor
      v-for="(f, index) in floors"
      :left="f[0]"
      :top="f[1]"
      :key="index"></floor>
  </div>
</template>

<script>

import Floor from '@/components/floor'

const MAX_NUM_OF_SHEEP = 20;


export default {
  name: "App",
  components: {
    Floor,
  },
  mounted() {
    setInterval(this.addSheep, (Math.floor(Math.random() * 5) + 2) * 1000);
  },
  methods: {
    addSheep() {
      if (this.sheep.length < MAX_NUM_OF_SHEEP) {
        let sheep = new eSheep({allowPopup: 'no'});
        sheep.Start();
        this.sheep.push(sheep);
      }
    },
    clearAllSheep() {
      this.sheep.forEach((s) => s.remove());
      this.sheep = [];
    }
  },
  data() {
    return {
      floors: [
        ['5%', '13%'],
        ['70%', '20%'],
        ['38%', '34%'],
        ['15%', '55%'],
        ['60%', '65%'],
      ],
      sheep: [],
      MAX_NUM_OF_SHEEP,
    };
  }
};
</script>

<style lang="scss">
  body {
    background: url(assets/background.jpg) no-repeat center center fixed;
    background-size: cover;
  }
  .clear-btn-container {
    text-align: right;
    button:not([disabled]) {
      &:hover {
        cursor: pointer;
      }
    }
  }
</style>
