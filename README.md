# @bitjourney/react-intl-dts [![npm version](https://badge.fury.io/js/%40bitjourney%2Freact-intl-dts.svg)](https://badge.fury.io/js/%40bitjourney%2Freact-intl-dts)

react-intl-dts is based on [i18n-dts](https://github.com/quipper/i18n-dts). Thank you!

`react-intl-dts` is a `d.ts` file generator for [react-intl](https://github.com/yahoo/react-intl).

With generated `d.ts` file you can treat `FormattedMessage` component type-safely!

## Installation

#### NPM

```sh
npm install -D @bitjourney/react-intl-dts
```

#### Yarn

```sh
yarn add -D @bitjourney/react-intl-dts
```

## Configuration

First of all specify the following settings in root `package.json`.

- `model`: file extension type can be either `.json`, `.ts` or `.js`
- `outputDir`: `d.ts` file will be emitted in specified directory

```json
"react-intl-dts": {
  "model": "./src/locale/languages/en.json",
  "outputDir": "./typings"
}
```

Note that when you specify `.ts` or `.js` file type as a model, use `module.exports` to export an object.

```ts
module.exports = {
  platform: {
    ios: 'Press Cmd+R to reload,\nCmd+D or shake for dev menu',
  },
};
```

And add `outputDir` dir into `filesGlob` option in `tsconfig.json`.

```json
"filesGlob": [
  "typings/*.d.ts",
],
```

That's it! Now you can use `react-intl-dts` command which generates corresponding `d.ts` file.

We recommend to add scripts below into `package.json`.

```json
"scripts": {
  "react-intl-dts": "react-intl-dts",
  "react-intl-dts:watch": "react-intl-dts -w"
},
```

## Options

### Watch mode

You can enable watch mode by adding `--watch` (shorthand `-w`) flag.

In the watch mode, react-intl-dts watches update of model file and generates d.ts file when the model is updated.

```sh
react-intl-dts --watch
```

## Licence

```
Copyright 2019 Bit Journey, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

### i18n-dts's license

react-intl-dts is based on i18n-dts.

```
Copyright 2018 Quipper Limited.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
