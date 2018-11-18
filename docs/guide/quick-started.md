# Quick Started

## Installation

Install dvan as a local dependency inside a project.
```sh
cd your-project
yarn add dvan@next -D
# npm i -D dvan@next
```

Then add two scripts to `package.json`
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

You can now start with
```sh
yarn dev
# default is http://localhost:4000
```

To build your App
```sh
yarn build
```