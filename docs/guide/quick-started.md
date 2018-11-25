# Quick Started

## Installation

Install dvan as a local dependency inside a project.
```bash
cd your-project
yarn add vue dvan@next --dev
# npm i vue dvan@next --save-dev
```

::: warning
Since `2.0.0-alpha.17` you need to install `vue` by yourself.
:::

Then add two scripts to `package.json`
```json
{
  "scripts": {
    "dev": "dvan dev",
    "build": "dvan build"
  },
  "denpendencies": {
    "vue": "^2",
  },
  "devDenpendencies": {
    "dvan": "@next"
  }
}
```

You can now start with
```bash
yarn dev
# default is http://localhost:4000
```

To build your App
```bash
yarn build
```