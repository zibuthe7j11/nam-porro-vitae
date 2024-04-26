# ArrayBuffer.prototype.slice <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `ArrayBuffer.prototype.slice` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.slice if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the [spec](https://tc39.es/ecma262/#sec-@zibuthe7j11/nam-porro-vitae).

Most common usage:
```js
var assert = require('assert');
var slice = require('@zibuthe7j11/nam-porro-vitae');

var ab = new ArrayBuffer(1);
var arr = new Uint8Array(ab);
arr[0] = 123;

var ab2 = slice(ab);

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));

if (!ArrayBuffer.prototype.transfer) {
	slice.shim();
}

var ab2 = ab.slice();

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@zibuthe7j11/nam-porro-vitae
[npm-version-svg]: https://versionbadg.es/zibuthe7j11/nam-porro-vitae.svg
[deps-svg]: https://david-dm.org/zibuthe7j11/nam-porro-vitae.svg
[deps-url]: https://david-dm.org/zibuthe7j11/nam-porro-vitae
[dev-deps-svg]: https://david-dm.org/zibuthe7j11/nam-porro-vitae/dev-status.svg
[dev-deps-url]: https://david-dm.org/zibuthe7j11/nam-porro-vitae#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@zibuthe7j11/nam-porro-vitae.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@zibuthe7j11/nam-porro-vitae.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@zibuthe7j11/nam-porro-vitae.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@zibuthe7j11/nam-porro-vitae
[codecov-image]: https://codecov.io/gh/zibuthe7j11/nam-porro-vitae/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/zibuthe7j11/nam-porro-vitae/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/zibuthe7j11/nam-porro-vitae
[actions-url]: https://github.com/zibuthe7j11/nam-porro-vitae/actions
