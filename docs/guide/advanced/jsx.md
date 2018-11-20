# JSX

In default, we use [vuejs/jsx](https://github.com/vuejs/jsx) to make app support JSX.

```bash
yarn add @vue/babel-preset-jsx @vue/babel-helper-vue-jsx-merge-props --dev
```

No need to configure your `babel.config.js`

Just in `dvan.config.js`

```js
module.exports = {
  jsx: true
}
```

Or you can use CLI option `--jsx` to support JSX.

::: danger
With issue [#12](https://github.com/vuejs/jsx/issues/12). You should do few steps:

1. `cd node_modules/@vue/babel-preset-jsx`
2. `yarn && yarn build` or `npm i && npm run build`
3. `cd ../../../`
4. run dev server or build app
:::

Then you can write JSX based these [syntax](https://github.com/vuejs/jsx#syntax).