---
sidebar: auto
---

# Config

## entry
- Type: `string`
- Default: `index`
- CLI: `dvan [...entries]`

Entry file(s).

## srcDir
- Type: `string`
- Default: `'src'`
- CLI: `-s, --src-dir <dir>`

The source directory of your App.

## outDir
- Type: `string`
- Default: `'__dist'`
- CLI: `-d, --out-dir <dir>`

The directory to generate App files.

## publicPath
- Type: `string`
- Default: `'/'`
- CLI: `--public-path <path>`

The all assets file URL prefix used in generated HTML files. It's usually use to deploy to a site under sub-path, i.e. `https://yoursite.com/rest/`, that should be set it to `/rest/`.

## html
- Type: `object`
- Default: `DefaultOptions`
- CLI: `--html[option] [value]` e.g. `--html.title myApp`

```js
const DefaultOptions = {
  template: `built-in-template-path`,
  filename: 'index.html',
  title: 'Dvan App'
}
```

Fully options in [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin#options)

## sourceMap
- Type: `boolean`
- Default: `true`
- CLI: `--[no-]source-map`

Sourcemaps for `.js` and `.css` files are also generated when compiled.

## minimize
- Type: `boolean | MinimizeOptions`
- Default: `true` in production mode, `false` otherwise
- CLI: `--[no-]minimize`

Minimize bundled `.js` and `.css` files.

```ts
interface MinimizeOptions {
  // Options for terser-webpack-plugin
  js?: any
  // Options for optimize-cssnano-plugin
  css?: any
}
```

See also

[terser-webpack-plugin#options](https://github.com/webpack-contrib/terser-webpack-plugin#options)

[optimize-cssnano-plugin](https://github.com/intervolga/optimize-cssnano-plugin)

## constants
- Type: `object`
- CLI: `--constants[option] [value]`

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
- CLI: `--[no-]extract-css`

Whether to extract CSS into standalone `.css` file(s).

## loaderOptions
- Type: `LoaderOptions`

Options for using loaders.

```ts
interface LoaderOptions {
  css?: any
  postcss?: any
  sass?: any
  less?: any
  stylus?: any
  babel?: any,
  vue?: any,
  artTemplate?: any
}
```

## jsx
- Type: `boolean|string`
- Default: `false`
- Values: `true|react` `vue` `h` or other JSX pragma
- CLI: `--jsx [syntax]`

<!-- Make app support JSX syntax. See [jsx-guide](/guide/advanced/jsx.md). -->

## chainWebpack
- Type: `(config => WebpackChain, opts: Opts) => void`

Internal webpack config with [webpack-chain](https://github.com/neutrinojs/webpack-chain)