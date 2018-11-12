---
sidebar: auto
---

# Config

## outDir
- Type: `string`
- Default: `__dist`

The directory to generate App files.

## publicPath
- Type: `string`
- Default: `/`

The all assets file URL prefix used in generated HTML files. It's usually use to deploy to a site under sub-path, i.e. `https://yoursite.com/rest/`, that should be set it to `/rest/`.

## html
- Type: `object`

Basically options:

- title
  - Type: `string`
  - Default: `'Dvan App'`
  - The title for the `<title></title>` in the generated HTML file.
- template
  - Type: `string<path>`
  - Default: `built-in template`
  - The template HTML file to render the generated HTML file.
- ...fully options in [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin#options)

## pagesDir
- Type: `string<path>`
- Default: `pages`

The directory to page files.

## match
- Type: `string` `RegExp`
- Default: `vue,js`

It used to match page components.

## sourceMap
- Type: `boolean`
- Default: `true`

Sourcemaps for `.js` and `.css` files are also generated when compiled.

## minimize
- Type: `boolean|object`
- Default: `'auto'` which means `true` in production build, `false` otherwise

Minimize bundled `.js` and `.css` files.
If set it an object please check out the following 2 options

## minimize.js
- Type: `object`

Options for [uglifyjs-webpack-plugin](https://www.npmjs.com/package/uglifyjs-webpack-plugin#options)

## minimize.css
- Type: `object`

Options for [optimize-css-assets-webpack-plugin](https://www.npmjs.com/package/optimize-css-assets-webpack-plugin)

## constants
- Type: `object`

Create global constants which can be configured at compile time.

## devServer
- Type: `object`
- Default: `{ host: '0.0.0.0', port: 4000 }`

Options for [webpack-dev-server](https://webpack.js.org/configuration/dev-server/#devserver)

## css.extract
- Type: `boolean`
- Default: `'auto'` which means `true` in production build, `false` otherwise

Whether to extract CSS into standalone `.css` file(s).

## css.loaderOptions
- Type: `object`

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

## chainWebpack
- Type: `(config => WebpackChain, opts: Opts) => void`

Internal webpack config with [webpack-chain](https://github.com/neutrinojs/webpack-chain)