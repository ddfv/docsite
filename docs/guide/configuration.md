# Configuration

## Config File
```
.
├── dvan.config.js
└── package.json
```

The config file for configuration your site, it should be export a JavaScript object:
```js
module.exports = {
  html: {
    title: 'Example'
  }
}
```

The full list of configuration options check out [Config](/config/).

Also work with

- `dvan.config.toml`
- `dvan.config.{yml,yaml}`

But need to install `toml` or `js-yaml` module by yourself.

## Enhancements

Each enhance file should `export default` a hook function which will be imported into the app if it is present. You can use this hook to install additional Vue plugins, register global components, or add additional router hooks:

```js
export default ({
  Vue, // the version of Vue being used in the app
  options, // the options for the root Vue instance
  router // the router instance for the app
}) => {
  // ...apply enhancements to the app
}
```

Structure looks like

```bash
.
├── enhancements
│   ├── ajax.js
│   └── ui-library.js
├── pages
├── dvan.config.js
└── package.json
```

::: tip
Split enhance-file will be easy to maintain.
:::

You can have reference via [enhancements-example](https://github.com/dvanjs/dvan-example/tree/master/enhancements) directly.
