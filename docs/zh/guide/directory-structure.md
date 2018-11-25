# 目录结构

## 目录

一个初始项目目录结构大致如下:

```bash
.
├── src                 # 必须.
│   ├── plugins         # 可选, 定制 App.
│   └── pages           # 可选, 无文件则显示一个 404 页面.
├── babel.config.js     # 可选, babel 配置.
├── dvan.config.js      # 可选.
└── package.json
```

你可以直接参考 [dvan-example](https://github.com/dvanjs/dvan-example).

### pages

页面文件目录.

```bash
src
└── pages
    ├── 404.vue     # 可选, 存在则替换默认 404 页面.
    └── index.vue
```

### plugins

每一个插件文件应该导出一个`export default`钩子函数, 当文件存在时, 会被导入到应用内部. 你可以使用这个钩子来安装一些附加的 Vue 插件、注册全局组件，或者增加额外的路由钩子等:

```js
export default ({
  Vue, // 应用正在使用的 Vue 构造函数
  options, // 附加到根实例的一些选项
  router // 当前应用路由实例
}) => {
  // ...应用一些其他插件
}
```

例如

```bash
src
└── plugins
    ├── ajax.js
    └── ui-library.js
```

::: tip
分割插件文件更易于维护
:::

## 目录修饰符

|目录|介绍|修饰符|默认|是否可配置|
|-|-|-|-|-|
|src|App 源目录|`@`|`src`|O|
|root|项目根目录|`@@`|`process.cwd()`|X|
|pages|页面目录|`@pages`||X|