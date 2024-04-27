# @wemnyelezxnpm/soluta-aspernatur-id <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES5 spec-compliant `Array.prototype.map` shim/polyfill/replacement that works as far down as ES3.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://www.ecma-international.org/ecma-262/5.1/).

Because `Array.prototype.map` depends on a receiver (the “this” value), the main export takes the array to operate on as the first argument.

## Example

```js
var map = require('@wemnyelezxnpm/soluta-aspernatur-id');
var assert = require('assert');

assert.deepEqual(map([1, 1, 1], function (x) { return x + 1; }), [2, 2, 2]);
assert.deepEqual(map([1, 0, 1], function (x) { return x + 1; }), [2, 1, 2]);
```

```js
var map = require('@wemnyelezxnpm/soluta-aspernatur-id');
var assert = require('assert');
/* when Array#map is not present */
delete Array.prototype.map;
var shimmedMap = map.shim();
assert.equal(shimmedMap, map.getPolyfill());
var arr = [1, 2, 3];
var add4 = function (x) { return x + 4; };
assert.deepEqual(arr.map(add4), map(arr, add4));
```

```js
var map = require('@wemnyelezxnpm/soluta-aspernatur-id');
var assert = require('assert');
/* when Array#map is present */
var shimmedMap = map.shim();
assert.equal(shimmedMap, Array.prototype.map);
assert.deepEqual(arr.map(add4), map(arr, add4));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@wemnyelezxnpm/soluta-aspernatur-id
[npm-version-svg]: https://versionbadg.es/wemnyelezxnpm/soluta-aspernatur-id.svg
[deps-svg]: https://david-dm.org/wemnyelezxnpm/soluta-aspernatur-id.svg
[deps-url]: https://david-dm.org/wemnyelezxnpm/soluta-aspernatur-id
[dev-deps-svg]: https://david-dm.org/wemnyelezxnpm/soluta-aspernatur-id/dev-status.svg
[dev-deps-url]: https://david-dm.org/wemnyelezxnpm/soluta-aspernatur-id#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@wemnyelezxnpm/soluta-aspernatur-id.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@wemnyelezxnpm/soluta-aspernatur-id.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@wemnyelezxnpm/soluta-aspernatur-id.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@wemnyelezxnpm/soluta-aspernatur-id
[codecov-image]: https://codecov.io/gh/wemnyelezxnpm/soluta-aspernatur-id/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/wemnyelezxnpm/soluta-aspernatur-id/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/wemnyelezxnpm/soluta-aspernatur-id
[actions-url]: https://github.com/wemnyelezxnpm/soluta-aspernatur-id/actions
