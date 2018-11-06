# Quick Started

## Installation

Install dvan as a local dependency inside a project.
```bash
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
    "dvan": "next"
  }
}
```

You can now start with:
```bash
yarn dev
# default is http://localhost:4000
```

To generate static assets:
```bash
yarn build
```