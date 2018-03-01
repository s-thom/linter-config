# Stuart's Linter Configs

This package contains linter configs for ESLint (and soon TSLint).

## Usage

```sh
npm install --save-dev @sthom/linter-config
```

Then reference it in your project's linter config (shown below).

### ESLint

The default configuration is for browser when using a transpiler (like Babel). Using it in your own project is easy:

```js
// .eslintrc.json
{
  "extends": [
    "./node_modules/@sthom/linter-config/.eslintrc.json"
  ]
}
```

*Note: Due to how ESLint's module resoution handles scoped packages you need to specify the full path.*

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


### TSLint (Coming Soon)

The default configuration is for browser with no major libraries. Using it in your own project is easy:

```js
// tslint.json
{
  "extends": [
    "@sthom/linter-config"
  ]
}
```

Alternate versions of the config are available, as follows:

* `@sthom/linter-config/tslint.jsx.json`
  * Add rules to deal with JSX syntax

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
if (oneTrueBraceStyle.isBest()) {
  oneTrueBraceStyle.use();
}
```

### Semicolons: Always

```js
const isUnambiguousStatement = true;
```

### Indentation: 2 Spaces

```js
indentation
  .view()
  .then(formOpinion)
  .then((opinion) => {
    return opinion
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
