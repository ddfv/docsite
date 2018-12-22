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
module.exports = {}
```

The full list of configuration options check out [Config](/config/).

Also work with

- `.dvanrc`
- `.dvanrc.{js,json,toml,yml,yaml}`
- `dvan.config.{js,json,toml,yml,yaml}`

But need to install `toml, toml-loader` or `js-yaml, yaml-loader` module by yourself.