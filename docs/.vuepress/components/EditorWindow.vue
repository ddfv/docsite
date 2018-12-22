<template>
  <div class="window editor-window">
    <div class="titlebar">
      <TrafficLight focus />
    </div>
    <div class="editor-content">
      <div class="tabs">
        <div
          class="tab"
          v-for="({ menu, name }, index) in files"
          :key="index"
          :class="{ active: currentIndex === index }"
          :style="{
            paddingLeft: (menu || 0) * 10 + 10 + 'px',
            paddingRight: '10px'
          }"
          @click="currentIndex = index">
          {{ name }}
        </div>
      </div>

      <div class="editor-codes">
        <pre><code v-html="code" /></pre>
      </div>
    </div>
  </div>
</template>

<script>
import Prism from 'prismjs'

export default {
  props: {
    files: {
      type: Array,
      required: true
    },
    msg: {
      type: String,
      required: true
    }
  },

  data() {
    return {
      currentIndex: 1 // App.vue
    }
  },

  computed: {
    currentFile() {
      return this.files[this.currentIndex]
    },
    code() {
      if (this.currentFile.msg) {
        this.$emit('update:msg', this.currentFile.msg)
      }
      if (this.currentFile.code) {
        return Prism.highlight(
          this.currentFile.code,
          Prism.languages[this.currentFile.lang],
          this.currentFile.lang
        )
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.editor-window
  display flex
  flex-direction column
  background rgb(40, 44, 52)

.titlebar
  display flex
  height 2em
  line-height 2em
  box-shadow rgb(24, 26, 31) 0 0 0 1px
  background-color rgb(33, 37, 43)
  z-index 1


.editor-content
  display flex

  .tabs
    display flex
    flex-direction column

  .tab
    color rgb(150, 150, 150)
    height 2em
    line-height 2em
    font-size 13px
    background-color rgb(33, 37, 43)
    &:hover
      background-color lighten(rgb(40, 44, 52), 5)
      cursor pointer
      user-select none
    &.active
      color #fff
      background-color rgb(40, 44, 52)
  .editor-codes
    padding 0 10px
    pre
      background-color transparent
      margin 0
      padding 0
</style>
