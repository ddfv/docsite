---
sidebar: auto
---

# 插件

## 编写插件

### 概述

```js
exports.name = 'my-plugin'

exports.extend = api => {
  // ...
}
```

### 属性

#### name
- 类型: `String`
- 是否需要: `false`

命名你的插件用于区分正在应用的所有插件.

#### extend
- 类型: `(api: PluginAPI, options: any) => void`
- 是否需要: `true`

参考 [PluginAPI](#plugin-api)

## 使用插件
这是一个应用插件的例子 [plugin-ssg](#ssg)

安装
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

使用本地插件
```js
module.exports = {
  plugins: [
    require('./plugins/my-plugin'),
    {
      // 可使用对象
      name: 'my-second-plugin',
      extend: api => {
        // ...
      }
    }
  ]
}
```

更多插件查阅 [插件列表](#plugins-list).


## 插件 API

### api.command
- 类型: `string`

获取当前命令.

### api.mode
- 类型: `string`

获取构建模式.

### api.resolve
基于项目目录的路径.

```js
api.resolve('pages')
```

### api.chainWebpack
通过 [webpack-chain](https://github.com/neutrinojs/webpack-chain) 来修改内部配置.

```js
api.chainWebpack(config => {
  // `config` 是一个 webpack-chain 实例
})
```


## 插件列表

### SSG <Badge text="alpha" type="warning"/>
> Static site generate

- Package: `@dvan/plugin-ssg`
- Command: `generate`

添加命令到 `package.json`

```json {5}
{
  "script": {
    "dev": "dvan dev",
    "build": "dvan build",
    "generate": "dvan generate"
  }
}
```

生成静态资源

```bash
yarn generate
```

#### 附加

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

或者可以通过设置 `dvan.config.js` 中的 `html` 字段来配置全部生成的 HTML 的 meta.

### PWA
> Progressive web application

TODO

### Blogging
TODO