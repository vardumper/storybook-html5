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

The primary way to use this addon is to define the `injectHTML5` parameter. You can do this the
component level, as below, to affect all stories in the file, or you can do it for a single story.

```js
// Button.stories.ts

// Replace your-framework with the name of your framework
import type { Meta } from '@storybook/your-framework';

import { Button } from './Button';

const meta: Meta<typeof Button> = {
  component: Button,
  parameters: {
    storybookHtml5: {
      injectHtml5: true,
      // See API section below for available parameters
    }
  }
};

export default meta;
```

Another way to use the addon is...

## API

### Parameters

This addon contributes the following parameters to Storybook, under the `storybookHtml5` namespace:

#### `disable`

Type: `boolean`

Disable this addon's behavior. This parameter is most useful to allow overriding at more specific
levels. For example, if this parameter is set to true at the project level, it could then be
re-enabled by setting it to false at the meta (component) or story level.

### Options

When registering this addon, you can configure it with the following options, which are passed when
registering the addon, like so:

```ts
// .storybook/main.ts

// Replace your-framework with the framework you are using (e.g., react-webpack5, vue3-vite)
import type { StorybookConfig } from '@storybook/your-framework';

const config: StorybookConfig = {
  // ...rest of config
  addons: [
    '@storybook/essentials',
    {
      name: 'storybookHtml5',
      options: {
        useFaker: true, // 👈 when true fake texts will be used, if false args will be empty
      },
    },
  ],
};

export default config;
```

#### `useExperimentalBehavior`

Type: `boolean`

Enable experimental behavior to...

### Icons

<img src='https://github.com/vardumper/storybook-html5/assets/21208397/c8d73198-0135-4c48-a4ca-33ea1a744a02' title='html5' width='48' height='48'>
