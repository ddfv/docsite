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

### name
- Type: `String`
- Required: `false`

Name your plugin to distinguish all plugins in use.

### extend
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


## Plugins list

### SSG
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

### PWA
> Progressive web application

TODO

### Blogging
TODO


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