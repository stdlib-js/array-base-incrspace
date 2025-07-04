<!--

@license Apache-2.0

Copyright (c) 2021 The Stdlib Authors.

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

# incrspace

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Generate a linearly spaced numeric array according to a provided increment.

<section class="installation">

## Installation

```bash
npm install @stdlib/array-base-incrspace
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var incrspace = require( '@stdlib/array-base-incrspace' );
```

#### incrspace( start, stop, increment )

Generates a linearly spaced numeric `array` according to a provided `increment`.

```javascript
var arr = incrspace( 0, 11, 2 );
// returns [ 0, 2, 4, 6, 8, 10 ]
```

</section>

<!-- /.usage -->

<section class="notes">

### Notes

-   The output `array` is guaranteed to include the `start` value but does **not** include the `stop` value. Beware that values subsequent to the `start` value are subject to floating-point errors. Hence,

    ```javascript
    var arr = incrspace( 0.1, 0.5, 0.2 );
    // returns [ 0.1, ~0.3 ]
    ```

    where `arr[1]` is only guaranteed to be approximately equal to `0.3`.

    If you desire more control over element precision, consider using [roundn][@stdlib/math/base/special/roundn]:

    ```javascript
    var roundn = require( '@stdlib/math-base-special-roundn' );

    // Create an array subject to floating-point errors:
    var arr = incrspace( 0, 1.01, 0.02 );

    // Round each value to the nearest hundredth:
    var i;
    for ( i = 0; i < arr.length; i++ ) {
        arr[ i ] = roundn( arr[ i ], -2 );
    }

    console.log( arr.join( '\n' ) );
    ```

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var incrspace = require( '@stdlib/array-base-incrspace' );

var out = incrspace( 0, 10, 2 );
console.log( out.join( '\n' ) );

out = incrspace( 0, 11, 2 );
console.log( out.join( '\n' ) );

out = incrspace( 0, 1.01, 0.02 );
console.log( out.join( '\n' ) );

// Create an array using a negative increment:
out = incrspace( 10, 0, -2 );
console.log( out.join( '\n' ) );
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

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-incrspace.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-incrspace

[test-image]: https://github.com/stdlib-js/array-base-incrspace/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/array-base-incrspace/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-incrspace/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-incrspace?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-incrspace.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-incrspace/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-incrspace/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-base-incrspace/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-base-incrspace/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-base-incrspace/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-base-incrspace/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-base-incrspace/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-base-incrspace/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-incrspace/main/LICENSE

[@stdlib/math/base/special/roundn]: https://github.com/stdlib-js/math-base-special-roundn

</section>

<!-- /.links -->
