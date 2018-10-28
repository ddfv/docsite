<template>
  <div class="window browser-window">
    <div class="titlebar">
      <TrafficLight />
      <div class="address">{{ address }}</div>
    </div>
    <div class="window-body">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    address: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="stylus" scoped>
.browser-window
  display flex
  flex-direction column
  color #666
  background #fff

.window-body
  margin 8px

.titlebar
  display flex
  height 2em
  line-height 2em
  box-shadow rgb(204, 204, 204) 0 0 0 1px
  background-color rgb(222, 225, 230)
  position relative

.address
  color #8c8c8c
  background rgba(255, 255, 255, .65)
  border-radius 5px
  padding 0 2.2em
  height 22px
  line-height @height
  font-size 13px
  position absolute
  left 50%
  top 50%
  transform translate(-50%, -50%)
</style>
