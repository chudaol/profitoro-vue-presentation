<template>
  <div class="timer-holder">
    <div class="center-content">
      <svg class="timer" viewBox="0 0 200 200" preserveAspectRatio="xMinYMin meet" xmlns="http://www.w3.org/2000/svg">
        <circle class="bigCircle" r="100" cx="100" cy="100"></circle>
        <circle class="smallCircle" r="90" cx="100" cy="100"></circle>
        <path class="segment" :d="path"></path>
        <slot></slot>
        <text v-if="text != ''" class="text" x="100" y="100">
          {{text}}
        </text>
      </svg>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['angle', 'text'],
    computed: {
      path () {
        let x = 100 - 100 * Math.sin(Math.PI * this.angle / 180)
        let y = 100 - 100 * Math.cos(Math.PI * this.angle / 180)

        return this.angle <= 180 ? `M100,100 L100, 0 A100,100 0 0,0 ${x}, ${y} z` : `M100,100  L100, 0 A100,100 0 0,0 100, 200 A100,100 0 0,0 ${x}, ${y} z`
      }
    }
  }
</script>
<style scoped lang="scss">
  @import "../../assets/styles/main";

  .timer-holder {
    display: table;

    @include media-breakpoint-down(md) {
      margin-top: 80px;
      width: 300px;
      height: 300px;
    }
  }
  .bigCircle {
    fill: $color-red;
  }
  .smallCircle {
    fill: $color-primary;
  }
  .segment {
    fill: $color-red;
    opacity: 0.6;
  }
  .text {
    font-weight: lighter;
    opacity: .9;
    fill: $color-white;
    text-anchor: middle;
  }
  .timer {
    width: 100%;
    height: 100%;
    display: flex;

    @include media-breakpoint-down(md) {
      width: 300px;
      height: 300px;
    }
  }
</style>
