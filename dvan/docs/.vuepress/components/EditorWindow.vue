<template>
  <div class="window editor-window">
    <div class="titlebar">
      <TrafficLight focus />
    </div>
    <div class="editor-content">
      <div class="tabs">
        <div
          class="tab"
          :class="{ active: currentIndex === index }"
          v-for="(file, index) in files"
          :key="index"
          @click="currentIndex = index">
          {{ file.name }}
        </div>
      </div>
      <div class="editor-codes">
        <pre><code v-html="code"></code></pre>
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
    }
  },

  data () {
    return {
      currentIndex: 0
    }
  },

  computed: {
    currentFile () {
      return this.files[this.currentIndex]
    },
    code () {
      return Prism.highlight(
        this.currentFile.code,
        Prism.languages[this.currentFile.lang],
        this.currentFile.lang
      )
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
    padding 0 10px
    height 2em
    line-height 2em
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
    overflow scroll
    pre
      background-color transparent
      margin 0
      padding 0
</style>
