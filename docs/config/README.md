---
sidebar: auto
---

# Config

## srcDir
- Type: `string`
- Default: `'src'`

The source directory of your App.

## outDir
- Type: `string`
- Default: `'__dist'`

The directory to generate App files.

## publicPath
- Type: `string`
- Default: `'/'`

The all assets file URL prefix used in generated HTML files. It's usually use to deploy to a site under sub-path, i.e. `https://yoursite.com/rest/`, that should be set it to `/rest/`.

## html
- Type: `object`
- Default: `DefaultOptions`

```js
const DefaultOptions = {
  template: `built-in-template-path`,
  filename: 'index.html',
  title: 'Dvan App'
}
```

Fully options in [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin#options)

## match
- Type: `string` `RegExp`
- Default: `'vue,js'`

It used to match page components.

## routerMode
- Type: `string`
- Default: `'hash'` in browser, `'abstract'` in Node.js

Official description see [router.mode](https://router.vuejs.org/api/#mode)

## sourceMap
- Type: `boolean`
- Default: `true`

Sourcemaps for `.js` and `.css` files are also generated when compiled.

## minimize
- Type: `boolean | MinimizeOptions`
- Default: `true` in production mode, `false` otherwise

Minimize bundled `.js` and `.css` files.

```ts
interface MinimizeOptions {
  // Options for uglifyjs-webpack-plugin
  js?: any
  // Options for optimize-css-assets-webpack-plugin
  css?: any
}
```

See also

[uglifyjs-webpack-plugin](https://www.npmjs.com/package/uglifyjs-webpack-plugin#options)

[optimize-css-assets-webpack-plugin](https://www.npmjs.com/package/optimize-css-assets-webpack-plugin)

## constants
- Type: `object`

Create global constants which can be configured at compile time.

## devServer
- Type: `object`
- Default: `DefaultOptions`
- CLI: `--host <ip>` `--port <port>`

```js
const DefaultOptions = {
  host: '0.0.0.0',
  port: 4000
}
```

Options for [webpack-dev-server](https://webpack.js.org/configuration/dev-server/#devserver)

## css.extract
- Type: `boolean`
- Default: `true` in production mode, `false` otherwise

Whether to extract CSS into standalone `.css` file(s).

## css.loaderOptions
- Type: `LoaderOptions`

Options for CSS loaders.

```ts
interface LoaderOptions {
  // Options for css-loader
  css?: any
  // Options for postcss-loader
  postcss?: any
  // Options for sass-loader
  sass?: any
  // Options for less-loader
  less?: any
  // Options for stylus-loader
  stylus?: any
}
```

## jsx
- Type: `boolean`
- Default: `false`
- CLI: `--jsx`

Make app support JSX syntax. See [jsx-guide](/guide/advanced/jsx.md).

## chainWebpack
- Type: `(config => WebpackChain, opts: Opts) => void`

Internal webpack config with [webpack-chain](https://github.com/neutrinojs/webpack-chain)