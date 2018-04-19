<template>
  <div class="floor" :style="positionStyle"></div>
</template>

<script>
export default {
  name: "Floor",
  props: ['left', 'top'],
  data() {
    return {
     
    };
  },
  computed: {
      positionStyle() {
        return {
            left: this.left,
            top: this.top,
        }
      }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
    .floor {
        position: absolute;
        background-image: url(../assets/floor.jpg);
        background-size: 100% 100%;
        width: 25%;
        height: 50px;
        border: 1px solid #9E9E9E; // essential for the sheep
    }
</style>
