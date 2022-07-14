# nullthrows
An idiomatic way to enforce values not to be `null` or `undefined`, with first-class support for TypeScript. Very lightweight with no dependencies.

## Installation and usage
```sh
npm install @expo/nullthrows
```

```js
import process from 'node:process';
import nullthrows from '@expo/nullthrows';

// nodeEnv is guaranteed to be a string. If the environment variable is
// undefined, nullthrows throws a TypeError.
const nodeEnv = nullthrows(process.env.NODE_ENV);

// You can optionally provide a custom error message
const nodeEnv2 = nullthrows(process.env.NODE_ENV, `NODE_ENV must be defined`);
```

## API

### `function nullthrows<T>(value: T | null | undefined, message?: string): NonNullable<T>`

#### Parameters
- `value`: the value to enforce not to be `null` or `undefined`
- `message`: an optional error message to use in the thrown `TypeError` if the given value is `null` or `undefined`

#### Type parameters
- `T`: the static type of `value`

#### Return value
Returns `value` if it is neither `null` nor `undefined`.

#### Throws
Throws a `TypeError` if `value` is `null` or `undefined`.

## History
This package is a spiritual successor of [`nullthrows`](https://github.com/zertosh/nullthrows). The motivation for a new package was primarily to support using TypeScript with ES modules since the type declarations included with `nullthrows` produce type errors.



