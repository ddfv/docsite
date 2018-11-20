# JSX

默认我们使用 [vuejs/jsx](https://github.com/vuejs/jsx) 使应用支持JSX.

由于问题 [#12](https://github.com/vuejs/jsx/issues/12), 所以我们使用自己的仓库来解决这个问题, 或许我们会在这个问题得到修复之后继续使用 Vue 官方仓库.

```bash
yarn add @dvan/babel-preset-jsx --dev
```

无需配置`babel.config.js`

仅需要在`dvan.config.js`中配置如下

```js
module.exports = {
  jsx: true
}
```

或者在CLI添加`--jsx`选项.

然后就可以根据这些语法 [syntax](https://github.com/vuejs/jsx#syntax) 编写JSX了.