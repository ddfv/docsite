# Directory Structure

A started-up project directory structure looks like:
```
.
├── pages
│   │── 404.vue     # optional, if exists will instead of default 404 page.
│   └── index.vue
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

```
.
├── src
│   └── pages
│       │── 404.vue     # optional
│       └── index.vue
├── dvan.config.js
└── package.json
```