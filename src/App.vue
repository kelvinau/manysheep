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

export default {
  name: "App",
  components: {
    Floor,
  },
  mounted() {
    let sheep = new eSheep(); 
    sheep.Start(); 
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
