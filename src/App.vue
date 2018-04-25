<template>
  <div class="background">
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
    this.addSheep();
  },
  methods: {
    addSheep() {
      let sheep = new eSheep(); 
      sheep.Start(); 
      this.numOfSheep++;
      if (this.numOfSheep !== MAX_NUM_OF_SHEEP) {
          setTimeout(this.addSheep, (Math.floor(Math.random() * 10) + 5) * 1000);
      }
    },
  },
  data() {
    return {
      floors: [
        ['5%', '13%'],
        ['70%', '20%'],
        ['38%', '34%'],
        ['9%', '55%'],
        ['65%', '65%'],
      ],
      numOfSheep: 0,
    };
  }
};
</script>

<style lang="scss">
  body {
    background: url(assets/background.jpg) no-repeat center center fixed;
    background-size: cover;
  }
</style>
