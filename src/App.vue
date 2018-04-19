<template>
  <div>
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
        ['28%', '38%'],
        ['60%', '58%'],
        ['12%', '78%'],
      ],
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
</style>
