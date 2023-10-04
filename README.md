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


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Number of CPUs

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Number of CPUs.



<section class="usage">

## Usage

```javascript
import NUM_CPUS from 'https://cdn.jsdelivr.net/gh/stdlib-js/os-num-cpus@deno/mod.js';
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

```javascript
var proc = require( 'process' );
var cluster = require( 'cluster' );
import NUM_CPUS from 'https://cdn.jsdelivr.net/gh/stdlib-js/os-num-cpus@deno/mod.js';

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

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/os-num-cpus.svg
[npm-url]: https://npmjs.org/package/@stdlib/os-num-cpus

[test-image]: https://github.com/stdlib-js/os-num-cpus/actions/workflows/test.yml/badge.svg?branch=v0.1.1
[test-url]: https://github.com/stdlib-js/os-num-cpus/actions/workflows/test.yml?query=branch:v0.1.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/os-num-cpus/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/os-num-cpus?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/os-num-cpus.svg
[dependencies-url]: https://david-dm.org/stdlib-js/os-num-cpus/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[cli-section]: https://github.com/stdlib-js/os-num-cpus#cli
[cli-url]: https://github.com/stdlib-js/os-num-cpus/tree/cli
[@stdlib/os-num-cpus]: https://github.com/stdlib-js/os-num-cpus/tree/main

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
