# @diotoborg/nam-occaecati <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-proposal-compliant `Object.fromEntries` shim. Invoke its "shim" method to shim `Object.fromEntries` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [proposed spec](https://tc39.github.io/proposal-object-from-entries/).

Most common usage:
```js
var assert = require('assert');
var fromEntries = require('@diotoborg/nam-occaecati');

var obj = { a: 1, b: 2, c: 3 };
var actual = fromEntries(Object.entries(obj));

assert.deepEqual(obj, actual);

if (!Object.fromEntries) {
	fromEntries.shim();
}

assert.deepEqual(Object.fromEntries(Object.entries(obj)), obj);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@diotoborg/nam-occaecati
[npm-version-svg]: https://versionbadg.es/diotoborg/nam-occaecati.svg
[deps-svg]: https://david-dm.org/diotoborg/nam-occaecati.svg
[deps-url]: https://david-dm.org/diotoborg/nam-occaecati
[dev-deps-svg]: https://david-dm.org/diotoborg/nam-occaecati/dev-status.svg
[dev-deps-url]: https://david-dm.org/diotoborg/nam-occaecati#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@diotoborg/nam-occaecati.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@diotoborg/nam-occaecati.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@diotoborg/nam-occaecati.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@diotoborg/nam-occaecati
[codecov-image]: https://codecov.io/gh/diotoborg/nam-occaecati/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/diotoborg/nam-occaecati/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/diotoborg/nam-occaecati
[actions-url]: https://github.com/diotoborg/nam-occaecati/actions
