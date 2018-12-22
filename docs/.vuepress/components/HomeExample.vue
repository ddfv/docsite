<template>
  <div class="home-example columns">
    <div class="column">
      <EditorWindow :files="files" :msg.sync="msg" />
    </div>
    <div class="column">
      <BrowserWindow :address="address">
        <div v-html="msg" />
      </BrowserWindow>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      address: 'localhost:4000',
      msg: '',
      files: [
        {
          name: 'src',
          lang: 'html',
          code: `App.vue`
        },
        {
          menu: 1,
          name: 'App.vue',
          msg: '<h1>Hi there! 😋</h1>',
          lang: 'html',
          code: `<template>
  <h1>
    {{ hello }}
  </h1>
<\/tempalte>
<script>
export default {
  data() {
    return {
      hello: 'Hi there! 😋'
    }
  }
}
<\/script>`
        },
        {
          name: 'index.js',
          lang: 'js',
          code: `import Vue from 'vue'
import App from '@/App'

new Vue({
  el: '#app',
  render: h => h(App)
})`
        },
        {
          name: 'package.json',
          lang: 'js',
          code: `{
  "script": {
    "dev": "dvan --dev --open",
    "build": "dvan --prod"
  },
  "dependencies": {
    "vue": "..."
  },
  "devDependencies": {
    "dvan": "^2.1.0",
    "vue-template-compiler": "..."
  }
}`
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.home-example
  display flex
  margin-top 60px
  margin-bottom 40px

.column
  flex 1
  padding 0 1.5em

@media screen and (max-width: 768px)
  .home-example
    flex-direction column

  .column
    margin-bottom 1.5em
    padding 0
</style>

<style lang="stylus">
.window
  border-radius 7px
  box-shadow rgba(0, 0, 0, .25) 0 14px 50px 0,
    rgba(0, 0, 0, .5) 0 2px 10px 0
  overflow hidden
  width 100%
  height 350px
</style>

<style lang="stylus" scoped>
h1
  margin 0
</style>
