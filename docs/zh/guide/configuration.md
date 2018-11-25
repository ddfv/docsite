# 配置

## 配置文件

`dvan.config.js`

```
.
├── src
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

- `dvan.config.json`
- `dvan.config.toml`
- `dvan.config.{yml,yaml}`

但需要自行安装`toml`或者`js-yaml`.