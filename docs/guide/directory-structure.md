# Directory Structure

## Basic

A started-up project directory structure looks like:
```sh
.
├── pages
│   │── 404.vue       # optional, if exists will instead of default 404 page.
│   └── index.vue
├── babel.config.js   # optional, more babel config.
├── dvan.config.js
└── package.json
```

You can configure the pages directory with `pagesDir` field in `dvan.config.js`

Example

```js
module.exports = {
  pagesDir: 'src/pages'
}
```

Will be resolve under `src/pages` directory Vue components as pages:

```sh
.
├── src
│   └── pages
│       │── 404.vue     # optional
│       └── index.vue
├── babel.config.js     # optional
├── dvan.config.js
└── package.json
```

You can have reference via [dvan-example](https://github.com/dvanjs/dvan-example) directly.
