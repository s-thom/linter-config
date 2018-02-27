# Stuart's Linter Configs

This package contains linter configs for ESLint (and soon TSLint).

## Opinions

The linter configs contain opinions on how code should look. If you don't agree with these opinions, then here's some options:

1. Cry about it on Twitter
2. Fork, edit, and submit a pull-request
3. Override the rules in your own `.eslintrc` or `tslint.json`

## Highlights

Some examples of the config in use. Since the majority of rules are specified, this README would be huge if they all were explained.

### Editability

All rules for the linters have been specified. Some of those specifications are `"off"`, but at least they are there in the file. That means that if you want to make changes, you have a known base to work off (not something that can change in the linter itself).


### Style

Code-style rules have been set. They include:

#### One True Brace Style

```js
if (oneTrueBraceStyle.isBest()) {
  oneTrueBraceStyle.use();
}
```

#### Semicolons: Always

```js
const isUnambiguousStatement = true;
```

#### Indentation: 2 Spaces

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

#### Trailing Commas: Always

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

#### Quotes: Single

```js
const reason = 'IDK, I just started using single quotes years ago';
```

## Usage

### ESLint

The default configuration is for browser when using a transpiler (like Babel). Using it in your own project is easy:

```js
// .eslintrc.json
{
  "extends": [
    "@sthom/linter-config"
  ]
}
```

Alternate versions of the config are available, as follows:

* `@sthom/linter-config/.eslintrc.node.json`
  * Adds Node globals
  * Adds Node-specific rules
* `@sthom/linter-config/.eslintrc.jsx.json`
  * Add rules to deal with JSX syntax
* `@sthom/linter-config/.eslintrc.react.json`
  * Extends `.eslintrc.jsx.json` to support React


### TSLint (Coming Soon)

The default configuration is for browser when using a transpiler (like Babel). Using it in your own project is easy:

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
