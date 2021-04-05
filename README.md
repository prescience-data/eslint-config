# Opinionated ESLint

An opinionated ESLint config rigging package based on Rushstack.

## Base Config Setup

Modifies the base [Rushstack ESLint config](https://github.com/microsoft/rushstack/tree/master/stack/eslint-config) to:

- [x] Include import sorting.
- [x] Disable the demand for `I` interface prefixes.
- [x] Disables type specification for [Zod](https://github.com/colinhacks/zod/tree/v3) schema folders.
- [x] Enforce [no require imports](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-require-imports.md).
- [x] Disabled [no parameter properties](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-parameter-properties.md) to enforce public/protected/private.

## Usage

To implement this config in your project, add it to your `devDependencies` and setup your package `.eslintrc.js` file as follows:

```shell
$ npm install -d opinionated-eslint
$ npm install -d @rushstack/eslint-config
$ npm install -d @typescript-eslint/parser
```

```js
require("@rushstack/eslint-config/patch/modern-module-resolution")

module.exports = {
  extends: [
    "@rushstack/eslint-config/profile/node",
    "@rushstack/eslint-config/mixins/friendly-locals",
    "opinionated-eslint",
  ]
}
```


## IDE Setup

Make sure to set up your IDE to auto-apply the rules it can easily fix by enabling `"fix on save"`.


## References

- https://eslint.org/
- https://rushstack.io/pages/heft_tasks/eslint/
- https://github.com/microsoft/rushstack/tree/master/stack/eslint-config
