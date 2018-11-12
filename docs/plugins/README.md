---
sidebar: auto
---

# Plugins

## Write a plugin

### Overview
```js
exports.name = 'my-plugin'

exports.extend = api => {
  // ...
}
```

### Properties

#### name
- Type: `String`
- Required: `false`

Name your plugin to distinguish all plugins in use.

#### extend
- Type: `(api: PluginAPI, options: any) => void`
- Required: `true`

See [PluginAPI](#plugin-api)

## Use a plugin
Here an example for [plugin-ssg](#ssg)

Install
```bash
yarn add @dvan/plugin-ssg --dev
```

dvan.config.js
```js {3}
module.exports = {
  plugins: [
    '@dvan/plugin-ssg'
  ]
}
```

With local plugin
```js
module.exports = {
  plugins: [
    require('./plugins/my-plugin'),
    {
      // Also works with an object
      name: 'my-second-plugin',
      extend: api => {
        // ...
      }
    }
  ]
}
```

More plugins see [Plugins list](#plugins-list) for now.


## Plugin API

### api.command
- Type: `string`

Get current command.

### api.mode
- Type: `string`

Get bundler mode.

### api.resolve
Resolve path from base directory.

```js
api.resolve('pages')
```

### api.chainWebpack
Using [webpack-chain](https://github.com/neutrinojs/webpack-chain) to modify internal webpack config.

```js
api.chainWebpack(config => {
  // `config` is a webpack-chain instance
})
```


## Plugins list

### SSG <Badge text="alpha" type="warning"/>
> Static site generate

- Package: `@dvan/plugin-ssg`
- Command: `generate`

Add a new command to `package.json`

```json {5}
{
  "script": {
    "dev": "dvan dev",
    "build": "dvan build",
    "generate": "dvan generate"
  }
}
```

To generate static site

```bash
yarn generate
```

#### Extra

head meta for [vue-meta](https://github.com/declandewet/vue-meta/#readme)

```vue {3-6}
<script>
export default {
  head: {
    title: 'Current page own title',
    meta: [...]
  }
}
</script>
```

Or you can set global meta in `config.html`, it will be apply to all generated html files.

### PWA
> Progressive web application

TODO

### Blogging
TODO