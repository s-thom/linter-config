# Stuart's Linter Configs

This package contains linter configs for ESLint, TSLint, Stylelint, and Markdownlint. Get it on [NPM](https://www.npmjs.com/package/@sthom/linter-config).

## Usage

*As of version `1.1`, the linters themselves are marked as peerDependencies, so will need to be installed separately*

```sh
npm install --save-dev @sthom/linter-config

# ESLint required packages
npm install --save-dev eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react
# Note: "eslint-plugin-import" is not required if using 'vanilla' preset.
#       "eslint-plugin-jsx-a11y" and "eslint-plugin-react" are not required if using default or 'vanilla' preset.

# TSLint required packages
npm install --save-dev tslint tslint-eslint-rules

# Stylelint required packages
npm install --save-dev stylelint

# Markdownlint CLI
npm install --save-dev markdownlint-cli
```

Then reference the configuration in your project's linter config (shown below).

*Note: Due to how Node's module resoution handles scoped packages you need to specify the full path.*

### ESLint

The default configuration is for browser when using a transpiler (like Babel):

```js
// .eslintrc.json
{
  "extends": [
    "./node_modules/@sthom/linter-config/.eslintrc.json"
  ]
}
```

Alternate versions of the config are available, as follows:

* `./node_modules/@sthom/linter-config/.eslintrc.vanilla.json`
  * Rules for older versions of Javascript
  * No fancy ES6 features
* `./node_modules/@sthom/linter-config/.eslintrc.node.json`
  * Adds Node globals
  * Adds Node-specific rules
* `./node_modules/@sthom/linter-config/.eslintrc.jsx.json`
  * Add rules to deal with JSX syntax
* `./node_modules/@sthom/linter-config/.eslintrc.react.json`
  * Extends `.eslintrc.jsx.json` to support React

### TSLint

The default configuration is for pretty much everything, including JSX support:

```js
// tslint.json
{
  "extends": [
    "./node_modules/@sthom/linter-config/tslint.json"
  ]
}
```

### Stylelint

The default configuration can be used with any file supported by stylelint:

```js
// .stylelintrc
{
  "extends": "./node_modules/@sthom/linter-config/.stylelintrc"
}
```

### Markdownlint

The default configuration just deals with plain old Markdown:

```js
// .markdownlint.json or .markdownlintrc
{
  "extends": "./node_modules/@sthom/linter-config/.markdownlint.json"
}
```

## Contributing

Go ahead. Fork, edit, and submit a pull-request. Or even fork, edit, and release your own.

The linter configs are opinionated, but then any styleguide is. If it's not to your liking, then here's some options:

1. Change the rules you want in your own `.eslintrc.json` or `tslint.json`
2. Fork this config, edit it, then submit a pull request
3. Use a different configuration as your base

## Editability

All rules for the linters have been specified. Some of those specifications are `"off"`, but at least they are there in the file. That means that if you want to make changes, you have a known base to work off (not something that can change in the linter itself).

## Highlights

Some examples of the config in use. Since the majority of rules are specified, this README would be huge if they all were explained.

### One True Brace Style

```js
if (oneTrueBraceStyle.isBest) {
  oneTrueBraceStyle.use();
}
```

```css
.braces::after {
  content: '1tbs';
}
```

### Semicolons: Always

```js
const isUnambiguousStatement = true;
```

```css
.semi {
  visibility: visible;
}
```

### Indentation: 2 Spaces

```js
indentation
  .view()
  .then(formOpinion)
  .then(opinion =>
    opinion
      .inflate()
      .exaggerate()
      .blowOutOfProportion()
      .postToInternet();
  });
```

### Trailing Commas: Always

```diff
  // Bad
  const words = [
    'foo',
-   'bar'
+   'bar',
+   'baz'
  ];

  // Good
  const words = [
    'foo',
    'bar',
+   'baz',
  ];
```

### Quotes: Single

```js
const reason = 'IDK, I just started using single quotes years ago';
```
