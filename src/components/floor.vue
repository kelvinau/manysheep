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

<style lang="scss" scoped>
    $border-color: #9E9E9E;
    $fence-height: 7%;
    .floor {
        position: absolute;
        background-image: url(../assets/floor.jpg);
        background-size: 100% 100%;
        width: 25%;
        height: $fence-height;
        border: 1px solid $border-color; // essential for the sheep
        &:before, &:after {
            position: absolute;
            height: 50%;
            top: -50%;
            width: 1%;
            content: '';
            border: 1px solid $border-color;
            border-bottom: none;
            transform: translateY(calc(-#{$fence-height} - 1px));
            background-color: #eee;
        }
        &:after {
            right: 0;
        }
    }
</style>
