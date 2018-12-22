# Quick Started

## Installation

Install dvan as a local dependency inside a project.
```bash
cd your-project
yarn add dvan --dev
```

Then add two scripts to `package.json`
```json
{
  "scripts": {
    "dev": "dvan --dev",
    "build": "dvan --prod"
  },
  "devDenpendencies": {
    "dvan": "@latest"
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