# study-nextjs-rocketseat
studying the implementation of nextets rocketseat https://www.youtube.com/watch?v=1nVUfZg2dSA&amp;t=1003s

## Eslint configuration 

.eslintrc.json

```js
{
    "env": {
        "browser": true,
        "es2021": true,
        "node": true,
        "jest": true
    },
    "extends": [
        "plugin:react/recommended",
        "standard",
        "plugin:@typescript-eslint/recommended",
        "prettier/@typescript-eslint",
        "prettier/standard",
        "prettier/react"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "plugins": [
        "react",
        "@typescript-eslint",
        "prettier"
    ],
    "rules": {
      "prettier/prettier":"error",
      "react/prop-types":"off"
    }
}

```

.eslintignore

```js
node_modules
.next
/*.js
```

## Babel configuration

babel.config.js

```js
module.exports = {
  presets: ["next/babel"],
  plugins: [["styled-components", { ssr: true }], "inline-react-svg"],
};

```

## nextjs-images

next.env.d.ts

```js
/// <reference types="next" />
/// <reference types="next/types/global" />
/// <reference types="next-images" />

```

next.config.js

```js
const withImages = require("next-images");

module.exports = withImages({
  esModule: true,
});

```

## config application theme

config.d.ts

```js
import 'styled-components';
import theme from './theme';

export type Theme = typeof theme;

declare module 'styled-components'{
  export interface DefaultTheme extends Theme {
  }
}
```

## Config a new font to all application

_document.tsx

```js
render(){
    return (
      <Html lang='pt'>
        <Head>
          <meta charSet='utf-8'/>
            <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;900&display=swap" rel="stylesheet"/>
        </Head>
        <body>
          <Main/>
          <NextScript/>
        </body>
      </Html>
    )
  }
```

