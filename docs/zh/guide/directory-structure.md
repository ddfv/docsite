# 目录结构

## 基本

一个初始项目目录结构大致如下:
```sh
.
├── pages
│   │── 404.vue       # 可选, 如果存在则替换默认 404 页面.
│   └── index.vue
├── babel.config.js   # 可选, 其他的 babel 选项.
├── dvan.config.js
└── package.json
```

你可以在`dvan.config.js`配置`pagesDir`字段更换页面目录.

例如

```js
module.exports = {
  pagesDir: 'src/pages'
}
```

会将`src/pages`下的所有 Vue 组件解释为页面.

```sh
.
├── src
│   └── pages
│       │── 404.vue     # 可选
│       └── index.vue
├── babel.config.js     # 可选
├── dvan.config.js
└── package.json
```

你可以直接参考 [dvan-example](https://github.com/dvanjs/dvan-example).
