# @erboladaiorg/perspiciatis-dignissimos <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `Object.hasOwn` shim. Invoke its "shim" method to shim `Object.hasOwn` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.es/proposal-accessible-object-hasownproperty/).

Most common usage:
```js
var assert = require('assert');
var hasOwn = require('@erboladaiorg/perspiciatis-dignissimos');

var obj = { a: 1, b: 2 };

assert(hasOwn(obj, 'a'));
assert(hasOwn(obj, 'b'));
assert('toString' in obj && !hasOwn(obj, 'toString'));

if (!Object.hasOwn) {
	hasOwn.shim();
}

assert.deepEqual(Object.hasOwn(obj, 'a'), hasOwn(obj, 'a'));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@erboladaiorg/perspiciatis-dignissimos
[npm-version-svg]: https://versionbadg.es/erboladaiorg/perspiciatis-dignissimos.svg
[deps-svg]: https://david-dm.org/erboladaiorg/perspiciatis-dignissimos.svg
[deps-url]: https://david-dm.org/erboladaiorg/perspiciatis-dignissimos
[dev-deps-svg]: https://david-dm.org/erboladaiorg/perspiciatis-dignissimos/dev-status.svg
[dev-deps-url]: https://david-dm.org/erboladaiorg/perspiciatis-dignissimos#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@erboladaiorg/perspiciatis-dignissimos.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@erboladaiorg/perspiciatis-dignissimos.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@erboladaiorg/perspiciatis-dignissimos.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@erboladaiorg/perspiciatis-dignissimos
[codecov-image]: https://codecov.io/gh/erboladaiorg/perspiciatis-dignissimos/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/erboladaiorg/perspiciatis-dignissimos/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/erboladaiorg/perspiciatis-dignissimos
[actions-url]: https://github.com/erboladaiorg/perspiciatis-dignissimos/actions
