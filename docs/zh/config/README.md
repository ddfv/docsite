---
sidebar: auto
---

# 配置选项

## srcDir
- 类型: `string`
- 默认值: `src`

App 源文件目录.

## outDir
- 类型: `string`
- 默认值: `__dist`

用于存放构建应用的目录.

## publicPath
- 类型: `string`
- 默认值: `/`

所有静态资源的url前缀, 通常用于部署应用到一个站点的子路径. 例如 `https://yoursite.com/rest/`, 则应设置为 `/rest/`.

## html
- 类型: `object`

基本选项:

- title
  - 类型: `string`
  - 默认值: `'Dvan App'`
  - 生成的 HTML 的标题.
- template
  - 类型: `string<path>`
  - 默认值: `内置模板`
  - 用于生成的 HTML 的模板.
- ...全部选项参考 [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin#options)

## match
- 类型: `string` `RegExp`
- 默认值: `vue,js`

用于匹配页面文件.

## sourceMap
- 类型: `boolean`
- 默认值: `true`

编译时同时生成 `.js` 和 `.css` 的sourcemap文件.

## minimize
- 类型: `boolean|object`
- 默认值: `'auto'` 等于在生产模式设置为 `true`, 其他均为 `false`.

压缩 `.js` 和 `.css` 文件.
如果设置为对象请参阅接下来的2个选项

## minimize.js
- 类型: `object`

选项参考 [uglifyjs-webpack-plugin](https://www.npmjs.com/package/uglifyjs-webpack-plugin#options)

## minimize.css
- 类型: `object`

选项参考 [optimize-css-assets-webpack-plugin](https://www.npmjs.com/package/optimize-css-assets-webpack-plugin)

## constants
- 类型: `object`

创建在编译时可配置的全局变量.

## devServer
- 类型: `object`
- 默认值: `{ host: '0.0.0.0', port: 4000 }`
- CLI: `--host --port`

选项参考 [webpack-dev-server](https://webpack.js.org/configuration/dev-server/#devserver)

## css.extract
- 类型: `boolean`
- 默认值: `'auto'` 等于在生产模式设置为 `true`, 其他均为 `false`.

是否提取 `.css` 为单独的文件.

## css.loaderOptions
- 类型: `object`

```js
module.exports = {
  css: {
    loaderOptions: {
      // For css-loader
      css: {},
      // For sass-loader
      sass: {},
      // For less-loader
      less: {},
      // For stylus-loader
      stylus: {}
    }
  }
}
```

## jsx
- 类型: `boolean`
- 默认值: `false`
- CLI: `--jsx`

使应用支持JSX语法, 详细参阅 [jsx-guide](/zh/guide/advanced/jsx.md).

## chainWebpack
- 类型: `(config => WebpackChain, opts: Opts) => void`

通过 [webpack-chain](https://github.com/neutrinojs/webpack-chain) 来修改内部配置.