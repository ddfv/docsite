# 快速开始

## 安装

安装 Dvan 到你项目中为本地开发依赖.
```sh
cd your-project
yarn add dvan@next --dev
# npm i --dev dvan@next
```

在`package.json`中添加两条脚本
```json
{
  "scripts": {
    "dev": "dvan dev",
    "build": "dvan build"
  },
  "devDenpendency": {
    "dvan": "@next"
  }
}
```

即可启动开发模式
```sh
yarn dev
# default is http://localhost:4000
```

构建你的应用
```sh
yarn build
```