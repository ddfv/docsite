# JSX

默认我们使用 [vuejs/jsx](https://github.com/vuejs/jsx) 使应用支持JSX.

```bash
yarn add @vue/babel-preset-jsx @vue/babel-helper-vue-jsx-merge-props --dev
```

无需配置`babel.config.js`

仅需要在`dvan.config.js`中配置如下

```js
module.exports = {
  jsx: true
}
```

或者在CLI添加`--jsx`选项.

::: danger 警告
根据问题 [#12](https://github.com/vuejs/jsx/issues/12). 你需要做几个步骤:

1. `cd node_modules/@vue/babel-preset-jsx`
2. `yarn && yarn build` or `npm i && npm run build`
3. `cd ../../../`
4. run dev server or build app
:::

然后就可以根据这些语法 [syntax](https://github.com/vuejs/jsx#syntax) 编写JSX了.