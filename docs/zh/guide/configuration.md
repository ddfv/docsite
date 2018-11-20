# 配置

## 配置文件
```
.
├── dvan.config.js
└── package.json
```

用于配置你的应用的配置文件, 它应该导出一个JavaScript对象:

```js
module.exports = {
  html: {
    title: 'Example'
  }
}
```

全部配置选项请看 [Config](/config/).

同时也可以使用以下格式作为配置文件

- `dvan.config.toml`
- `dvan.config.{yml,yaml}`

但需要自行安装`toml`或者`js-yaml`.

## 应用级配置

每一个应用级配置文件应该导出一个`export default`钩子函数, 当文件存在时, 会被导入到应用内部. 你可以使用这个钩子来安装一些附加的 Vue 插件、注册全局组件，或者增加额外的路由钩子等:

```js
export default ({
  Vue, // 应用正在使用的 Vue 构造函数
  options, // 附加到根实例的一些选项
  router // 当前应用路由实例
}) => {
  // ...做一些其他应用级优化
}
```

结构看起来像这个样子

```bash
.
├── enhancements
│   ├── ajax.js
│   └── ui-library.js
├── pages
├── dvan.config.js
└── package.json
```

::: tip 提示
分割应用级配置文件将更易于维护.
:::

你可以直接参考 [enhancements-example](https://github.com/dvanjs/dvan-example/tree/master/enhancements).
