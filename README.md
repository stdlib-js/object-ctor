<!--

@license Apache-2.0

Copyright (c) 2022 The Stdlib Authors.

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

# Object

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Object][mdn-object] constructor.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/object-ctor
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
var Object = require( '@stdlib/object-ctor' );
```

#### Object( value )

Returns a new [object][mdn-object].

```javascript
var o = new Object( null );
// returns {}
```

* * *

### Properties

<a name="prop-constructor"></a>

#### Object.prototype.constructor

Property whose value is a reference to the constructor function that created the instance object.

```javascript
var o = new Object( null );
var ctr = o.constructor;
// returns Object
```

* * *

### Methods

<a name="static-method-assign"></a>

#### Object.assign( target, ...sources )

Assigns enumerable properties of one or more source objects to a target object.

```javascript
var o = Object.assign( {}, { 'a': 1, 'b': 2 } );
// returns { 'a': 1, 'b': 2 }
```

<a name="static-method-create"></a>

#### Object.create( prototype, properties )

Returns a new object with the given prototype and properties.

```javascript
var o = Object.create( null, {
    'a': {
        'value': 1
    },
    'b': {
        'value': 2
    }
});
// returns { 'a': 1, 'b': 2 }

function Person( first, last ) {
    this.first = first;
    this.last = last;
}

var p = Object.create( Person.prototype, {
    'first': {
        'value': 'Jane'
    },
    'last': {
        'value': 'Doe'
    }
});
// returns Person { 'first': 'Jane', 'last': 'Doe' }
```

<a name="static-method-define-properties"></a>

#### Object.defineProperties( target, properties )

Defines new or modifies existing properties directly on an object, returning the object.

```javascript
var o = Object.defineProperties( {}, {
    'a': {
        'value': 1
    },
    'b': {
        'value': 2
    }
});
// returns { 'a': 1, 'b': 2 }
```

<a name="static-method-define-property"></a>

#### Object.defineProperty( target, property, descriptor )

Defines a new property directly on an object, or modifies an existing property on an object, and returns the object.

```javascript
var o = Object.defineProperty( {}, 'a', {
    'value': 1,
    'writable': true,
    'enumerable': true,
    'configurable': true
});
// returns { 'a': 1 }
```

<a name="static-method-entries"></a>

#### Object.entries( obj )

Returns an array of a given object's own enumerable string-keyed property entries, i.e. `[key, value]` pairs.

```javascript
var o = { 'a': 1, 'b': 2 };
var arr = Object.entries( o );
// e.g., returns [ [ 'a', 1 ], [ 'b', 2 ] ]
```

<a name="static-method-freeze"></a>

#### Object.freeze( o )

Freezes an object. A frozen object can no longer be changed; freezing an object prevents new properties from being added to it, existing properties from being removed, and existing properties from being changed.

```javascript
var o = { 'a': 1 };
Object.freeze( o );
// returns { 'a': 1 }

o.b = 1;
var v = o.b;
// returns undefined
```

<a name="static-method-get-own-property-descriptor"></a>

#### Object.getOwnPropertyDescriptor( o, p )

Returns an object that contains the properties of the given object.

```javascript
var o = { 'a': 1 };
var d = Object.getOwnPropertyDescriptor( o, 'a' );
// returns { 'value': 1, 'writable': true, 'enumerable': true, 'configurable': true }
```

<a name="static-method-get-own-property-descriptors"></a>

#### Object.getOwnPropertyDescriptors( o )

Returns an object whose properties are the result of calling `Object.getOwnPropertyDescriptor()` on every property of the given object.

```javascript
var o = { 'a': 1, 'b': 2 };
var d = Object.getOwnPropertyDescriptors( o );
// returns { 'a': { 'value': 1, 'writable': true, 'enumerable': true, 'configurable': true }, 'b': { 'value': 2, 'writable': true, 'enumerable': true, 'configurable': true } }
```

<a name="static-method-get-own-property-names"></a>

#### Object.getOwnPropertyNames( o )

Returns an array of a given object's own property names.

```javascript
var o = { 'a': 1, 'b': 2 };
var arr = Object.getOwnPropertyNames( o );
// e.g., returns [ 'a', 'b' ]
```

<a name="static-method-get-own-property-symbols"></a>

#### Object.getOwnPropertySymbols( o )

Returns an array of a given object's own property symbols.

```javascript
var o = { 'a': 1 };
o[ Symbol( 'b' ) ] = 2;
var arr = Object.getOwnPropertySymbols( o );
// returns [ Symbol(b) ]
```

<a name="static-method-get-prototype-of"></a>

#### Object.getPrototypeOf( o )

Returns the prototype of an object.

```javascript
var o = { 'a': 1 };
var p = Object.getPrototypeOf( o );
// returns {}
```

<a name="static-method-has-own"></a>

#### Object.hasOwn( o, p )

Returns a boolean indicating whether an object has a property with the specified name.

```javascript
var o = { 'a': 1 };
var b = Object.hasOwn( o, 'b' );
// returns false
```

<a name="method-proto-has-own-prop"></a>

#### Object.prototype.hasOwnProperty( p )

Returns a boolean indicating whether an object has a property with the specified name.

```javascript
var o = { 'a': 1 };
var b = o.hasOwnProperty( 'a' );
// returns true
```

<a name="static-method-is"></a>

#### Object.is( value1, value2 )

Returns a boolean indicating whether two values are the same value.

```javascript
var b = Object.is( 1, 1 );
// returns true

b = Object.is( 1, '1' );
// returns false
```

<a name="static-method-is-extensible"></a>

#### Object.isExtensible( o )

Returns a boolean indicating whether an object is extensible (whether new properties can be added to it).

```javascript
var o = { 'a': 1 };
var b = Object.isExtensible( o );
// returns true

Object.preventExtensions( o );
b = Object.isExtensible( o );
// returns false
```

<a name="static-method-is-frozen"></a>

#### Object.isFrozen( o )

Returns a boolean indicating whether an object is frozen. Frozen objects can no longer be changed; freezing an object prevents new properties from being added to it, existing properties from being removed, and existing properties from being changed.

```javascript
var o = { 'a': 1 };
var b = Object.isFrozen( o );
// returns false

Object.freeze( o );
b = Object.isFrozen( o );
// returns true
```

<a name="method-is-prototype-of"></a>

#### Object.prototype.isPrototypeOf( o )

Returns a boolean indicating whether an object is in the prototype chain of another object.

```javascript
var o = { 'a': 1 };
var p = { '__proto__': o };
var b = o.isPrototypeOf( p );
// returns true
```

<a name="static-method-is-sealed"></a>

#### Object.isSealed( o )

Returns a boolean indicating whether an object is sealed. An object is sealed if it is not extensible and all of its properties are non-configurable.

```javascript
var o = { 'a': 1 };
var b = Object.isSealed( o );
// returns false

Object.seal( o );
b = Object.isSealed( o );
// returns true
```

<a name="static-method-keys"></a>

#### Object.keys( o )

Returns an array of a given object's own enumerable property names.

```javascript
var o = { 'a': 1, 'b': 2 };
var arr = Object.keys( o );
// e.g., returns [ 'a', 'b' ]
```

<a name="static-method-prevent-extensions"></a>

#### Object.preventExtensions( o )

Prevents new properties from being added to an object.

```javascript
var o = { 'a': 1 };
Object.preventExtensions( o );
o.b = 2;
var b = ( o.b === void 0 );
// returns true

o.a = 3;
b = ( o.a === 3 );
// returns true
```

<a name="method-prop-is-enumerable"></a>

#### Object.prototype.propertyIsEnumerable( p )

Returns a boolean indicating whether a property is enumerable.

```javascript
var o = { 'a': 1 };
var b = o.propertyIsEnumerable( 'a' );
// returns true

var arr = [ 1, 2, 3 ];
b = arr.propertyIsEnumerable( 'length' );
// returns false
```

<a name="static-method-seal"></a>

#### Object.seal( o )

Seals an object, preventing new properties from being added to it (i.e., making it non extensible) and marking all existing properties as non-configurable.

```javascript
var o = { 'a': 1 };
Object.seal( o );

o.b = 2;
var b = ( o.b === void 0 );
// returns true
```

<a name="static-method-set-prototype-of"></a>

#### Object.setPrototypeOf( o, proto )

Sets the prototype of an object.

```javascript
var o = { 'a': 1 };
var p = { 'b': 2 };
Object.setPrototypeOf( o, p );

var b = ( o.b === 2 );
// returns true
```

<a name="method-to-locale-string"></a>

#### Object.prototype.toLocaleString()

Returns a string representing the object.

```javascript
var o = { 'a': 1 };
var str = o.toLocaleString();
// returns <string>
```

<a name="method-to-string"></a>

#### Object.prototype.toString()

Returns a string representing the object.

```javascript
var o = { 'a': 1 };
var str = o.toString();
// returns <string>
```

<a name="method-to-value-of"></a>

#### Object.prototype.valueOf()

Returns the primitive value of the object.

```javascript
var o = {};
var v = o.valueOf();
// returns {}
```

<a name="static-method-values"></a>

#### Object.values( o )

Returns an array of a given object's own enumerable property values.

```javascript
var o = { 'a': 1, 'b': 2 };
var arr = Object.values( o );
// e.g., returns [ 1, 2 ]
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   If provided `null` or `undefined`, the function returns an empty object.
-   If provided an existing object, the function returns the input value unchanged.
-   Otherwise, if provided any other value (e.g., a number, string, etc), the function will return an object of the corresponding type.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var Object = require( '@stdlib/object-ctor' );

var values = [
    '5',
    5,
    true,
    false,
    null,
    void 0,
    [],
    {}
];

var i;
for ( i = 0; i < values.length; i++ ) {
    console.log( new Object( values[ i ] ) );
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

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

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/object-ctor.svg
[npm-url]: https://npmjs.org/package/@stdlib/object-ctor

[test-image]: https://github.com/stdlib-js/object-ctor/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/object-ctor/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/object-ctor/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/object-ctor?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/object-ctor.svg
[dependencies-url]: https://david-dm.org/stdlib-js/object-ctor/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/object-ctor/tree/deno
[deno-readme]: https://github.com/stdlib-js/object-ctor/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/object-ctor/tree/umd
[umd-readme]: https://github.com/stdlib-js/object-ctor/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/object-ctor/tree/esm
[esm-readme]: https://github.com/stdlib-js/object-ctor/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/object-ctor/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/object-ctor/main/LICENSE

[mdn-object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object

</section>

<!-- /.links -->
