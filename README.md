# npm-install-global [![NPM version](https://img.shields.io/npm/v/npm-install-global.svg?style=flat)](https://www.npmjs.com/package/npm-install-global) [![NPM downloads](https://img.shields.io/npm/dm/npm-install-global.svg?style=flat)](https://npmjs.org/package/npm-install-global) [![Build Status](https://img.shields.io/travis/jonschlinkert/npm-install-global.svg?style=flat)](https://travis-ci.org/jonschlinkert/npm-install-global)

Simple API for globally installing or uninstalling one or more NPM packages.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save npm-install-global
```

## Usage

```js
var npm = require('npm-install-global');

// easily install packages
npm.install('generate', function(err) {
  if (err) return console.log(err);
});

// or remove outdated packages
npm.uninstall('yeoman', function(err) {
  if (err) return console.log(err);
});

// or install only packages that don't already exist
npm.maybeInstall(['foo', 'bar'], function(err) {
  if (err) return console.log(err);
});
```

## API

### [npm](index.js#L29)

Execute `npm --global` with the given command and one or more package names. This is the base for [install](#install) and [uninstall](#uninstall).

**Params**

* `names` **{String|Array}**: One or more package names.
* `cb` **{Function}**: Callback

**Example**

```js
npm('install', 'verb', function(err) {
  if (err) throw err;
});
```

### [.install](index.js#L64)

Execute `npm install --global` with one or more package `names`.

**Params**

* `names` **{String|Array}**: One or more package names.
* `cb` **{Function}**: Callback

**Example**

```js
npm.install('generate', function(err) {
  if (err) throw err;
});
```

### [.maybeInstall](index.js#L81)

Install the given packages if they are not already installed.

**Params**

* `names` **{String|Array}**: One or more package names.
* `cb` **{Function}**: Callback

**Example**

```js
npm.maybeInstall(['foo', 'bar', 'baz'], function(err) {
  if (err) throw err;
});
```

### [.uninstall](index.js#L113)

Execute `npm uninstall --global` with one or more package `names`.

**Params**

* `names` **{String|Array}**: One or more package names.
* `cb` **{Function}**: Callback

**Example**

```js
npm.uninstall('yeoman', function(err) {
  if (err) throw err;
});
```

## History

**v0.1.1**

* adds [maybeInstall](#maybeInstall) method

## Related projects

You might also be interested in these projects:

* [base](https://www.npmjs.com/package/base): base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting… [more](https://github.com/node-base/base) | [homepage](https://github.com/node-base/base "base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting with a handful of common methods, like `set`, `get`, `del` and `use`.")
* [base-npm](https://www.npmjs.com/package/base-npm): Base plugin that adds methods for programmatically running npm commands. | [homepage](https://github.com/jonschlinkert/base-npm "Base plugin that adds methods for programmatically running npm commands.")
* [generate](https://www.npmjs.com/package/generate): Fast, composable, highly pluggable project generator with a user-friendly and expressive API. | [homepage](https://github.com/generate/generate "Fast, composable, highly pluggable project generator with a user-friendly and expressive API.")

## Contributing

This document was generated by [verb-readme-generator](https://github.com/verbose/verb-readme-generator) (a [verb](https://github.com/verbose/verb) generator), please don't edit directly. Any changes to the readme must be made in [.verb.md](.verb.md). See [Building Docs](#building-docs).

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new). Or visit the [verb-readme-generator](https://github.com/verbose/verb-readme-generator) project to submit bug reports or pull requests for the readme layout template.

## Building docs

Generate readme and API documentation with [verb](https://github.com/verbose/verb):

```sh
$ npm install -g verb verb-readme-generator && verb
```

## Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

## Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](LICENSE).

***

_This file was generated by [verb](https://github.com/verbose/verb), v0.9.0, on June 13, 2016._