<img src='https://github.com/vardumper/storybook-html5/assets/21208397/c8d73198-0135-4c48-a4ca-33ea1a744a02' style='float:left; margin-right:35px;' title='html5' width='48' height='48'>
# Storybook HTML5 Addon
Adds all HTML5 elements to your Storybook

## Installation

First, install the package.

```sh
npm install --save-dev storybook-html5
```

Then, register it as an addon in `.storybook/main.js`.

```js
// .storybook/main.ts

// Replace your-framework with the framework you are using (e.g., react-webpack5, vue3-vite)
import type { StorybookConfig } from '@storybook/your-framework';

const config: StorybookConfig = {
  // ...rest of config
  addons: [
    '@storybook/addon-essentials'
    'storybook-html5', // 👈 register the addon here
  ],
};

export default config;
```

## Usage

This addons adds a Yarn command to your Storybook project. Executing it will populate all HTML5 stories in your Storybook.

```
yarn storybook-html5
```
