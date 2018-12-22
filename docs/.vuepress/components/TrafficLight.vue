<template>
  <div class="traffic-light">
    <span class="dot" :class="{ 'dot-red': focus }" />
    <span class="dot" :class="{ 'dot-yellow': focus }" />
    <span class="dot" :class="{ 'dot-green': focus }" />
  </div>
</template>

<script>
export default {
  props: {
    focus: {
      type: Boolean,
      default: false
    }
  }
}
</script>


<style scoped lang="stylus">
.traffic-light
  margin 0 12px

.dot
  display inline-block
  width 12px
  height 12px
  margin 0 2px
  border-radius 50%
  background-color rgb(208, 208, 208)

.dot-red
  background-color rgb(252, 98, 93)
.dot-yellow
  background-color rgb(253, 191, 65)
.dot-green
  background-color rgb(53, 203, 75)
</style>
