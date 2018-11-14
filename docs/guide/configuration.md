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

If you prefer `dvan.config.toml` or `dvan.config.{yml,yaml}` to configure your app. You can use it to instead of `dvan.config.js` but need to install `toml` or `js-yaml` module by yourself.

<!-- ## Enhancement
To make your website more features. You can create a file `.dvan/enhanceApp.js`, it will be imported into the app if it present. The file should  `export default` a hook function which will receive an object containing some app values. You can use this hook to install additional Vue plugins, register global components, or add additional router hooks:
```js
export default ({
  Vue, // the version of Vue being used in the dvan app
  router // the router instance for the app
}) => {
  // ...apply enhancements to app
}
``` -->