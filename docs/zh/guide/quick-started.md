# 快速开始

## 安装

安装 Dvan 到你项目中为本地开发依赖.
```bash
cd your-project
yarn add vue
yarn add dvan@next --dev
```

::: warning ⚠️
从 `2.0.0-alpha.17` 需要自行安装 `vue`.
:::

在`package.json`中添加两条脚本
```json
{
  "scripts": {
    "dev": "dvan dev",
    "build": "dvan build"
  },
  "denpendencies": {
    "vue": "^2"
  },
  "devDenpendencies": {
    "dvan": "@next"
  }
}
```

即可启动开发模式
```bash
yarn dev
# default is http://localhost:4000
```

构建你的应用
```bash
yarn build
```