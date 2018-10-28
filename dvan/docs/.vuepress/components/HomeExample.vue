<template>
  <div class="home-example columns">
    <div class="column">
      <EditorWindow :files="files"/>
    </div>
    <div class="column">
      <BrowserWindow :address="address">
        <h1>{{ hello }}</h1>
      </BrowserWindow>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      address: 'localhost:4000',
      files: [
        {
          name: 'pages/index.vue',
          lang: 'html',
          code: `<template>
  <div>
    <h1>{{ hello }}</h1>
  </div>
<\/tempalte>
<script>
export default {
  data () {
    return {
      hello: 'Hello, Gorgeous!'
    }
  }
}
<\/script>`
        },
        {
          name: '.gitignore',
          lang: 'js',
          code: `dist`
        },
        {
          name: 'dvan.config.js',
          lang: 'js',
          code: `module.exports = {
  title: 'App'
}`
        },
        {
          name: 'package.json',
          lang: 'js',
          code: `{
  "script": {
    "dev": "dvan dev",
    "build": "dvan build"
  },
  "devDependencies": {
    "dvan": "@next"
  }
}`
        }
      ],
      hello: 'Hello, Gorgeous!'
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
