# Configuration

## Config File

`dvan.config.js`

```
.
├── src
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

- `dvan.config.json`
- `dvan.config.toml`
- `dvan.config.{yml,yaml}`

But need to install `toml` or `js-yaml` module by yourself.