<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# Number of CPUs

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Number of CPUs.



<section class="usage">

## Usage

To use in Observable,

```javascript
NUM_CPUS = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/os-num-cpus@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var NUM_CPUS = require( 'path/to/vendor/umd/os-num-cpus/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/os-num-cpus@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.NUM_CPUS;
})();
</script>
```

#### NUM_CPUS

Number of CPUs.

```javascript
var n = NUM_CPUS;
// returns <number>
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   In a web browser, the number of CPUs is determined by querying the hardware concurrency [API][hardware-concurrency].
-   Otherwise, the number of CPUs is determined via the [os][node-os] module.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- run-disable -->

<!-- eslint-disable node/no-process-exit -->

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript">
(function () {
var proc = require( 'process' );
var cluster = require( 'cluster' );
var NUM_CPUS = require( '@stdlib/os-num-cpus' );

var i;

function onTimeout() {
    proc.exit( 0 );
}

if ( cluster.isMaster ) {
    for ( i = 0; i < NUM_CPUS; i++ ) {
        cluster.fork();
    }
} else {
    console.log( 'Worker %s. Process id: %d.', cluster.worker.id, cluster.worker.process.pid );

    setTimeout( onTimeout, 1000 );
}

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->



<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/os-num-cpus.svg
[npm-url]: https://npmjs.org/package/@stdlib/os-num-cpus

[test-image]: https://github.com/stdlib-js/os-num-cpus/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/os-num-cpus/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/os-num-cpus/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/os-num-cpus?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/os-num-cpus.svg
[dependencies-url]: https://david-dm.org/stdlib-js/os-num-cpus/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/os-num-cpus/tree/deno
[umd-url]: https://github.com/stdlib-js/os-num-cpus/tree/umd
[esm-url]: https://github.com/stdlib-js/os-num-cpus/tree/esm
[branches-url]: https://github.com/stdlib-js/os-num-cpus/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/os-num-cpus/main/LICENSE

[node-os]: https://nodejs.org/api/os.html#os_os_cpus

[hardware-concurrency]: https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency

</section>

<!-- /.links -->
