# JSX

In default, we use [vuejs/jsx](https://github.com/vuejs/jsx) to make app support JSX.

But with issue [#12](https://github.com/vuejs/jsx/issues/12), so we change to use our repo to fix this issue. Maybe we'll use Vue official repo back when that issue have been fixed.

```bash
yarn add @dvan/babel-preset-jsx --dev
```

No need to configure your `babel.config.js`

Just in `dvan.config.js`

```js
module.exports = {
  jsx: true
}
```

Or you can use CLI option `--jsx` to support JSX.

Then you can write JSX based these [syntax](https://github.com/vuejs/jsx#syntax).