# Directory Structure

## Directories

A started-up App directory structure looks like:

```bash
.
├── src                 # required.
│   ├── plugins         # optional, make your app more feature.
│   └── pages           # optional, if no page component will show you a 404 page.
├── babel.config.js     # optional, more babel config.
├── dvan.config.js      # optional.
└── package.json        # no description.
```

You can have reference via [dvan-example](https://github.com/dvanjs/dvan-example) directly.

### pages

The directory to page files.

```bash
src
└── pages
    ├── 404.vue     # optional, if exists will instead of default 404 page.
    └── index.vue
```

### plugins

Each plugin file should `export default` a hook function which will be imported into the app if it is present. You can use this hook to install additional Vue plugins, register global components, or add additional router hooks:

```js
export default ({
  Vue, // the version of Vue being used in the app
  options, // the options for the root Vue instance
  router // the router instance for the app
}) => {
  // ...apply plugins to the app
}
```

e.g.

```bash
src
└── plugins
    ├── ajax.js
    └── ui-library.js
```

::: tip
Split plugin-file will be easy to maintain.
:::

## Aliases

|Directory|Alias|Default|Configurable|
|-|-|-|-|
|srcDir|`@`|`src`|O|
|rootDir|`@@`|`process.cwd()`|X|
|pagesDir|`@pages`||X|