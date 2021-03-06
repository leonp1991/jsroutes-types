# jsroutes-types

> Automatically generate flow types for code generated by the
> [js-routes](https://github.com/railsware/js-routes) gem for rails

## Installation

```sh
yarn add -D jsroutes-types # installs to your project - prefix CLI commands with `yarn`
# or
yarn add -g jsroutes-types # installs globally - use CLI commands as-is
# or
npm install jsroutes-types # if you use NPM
```

This exposes a CLI `jsroutes-types`, and an API (the default `require`)

## CLI

This is the main usage scenario.

To generate types for the routes, run:

```sh
jsroutes-types /path/to/generated/routes.js
```

and you should get a whole lot of types generated and printed to `stdout`.

You can specify the following options:

- `-o <file>, --output <file>` - output the types to a specific file
- `-x <ext>, --extension <ext>` - output to the same place as the input, but append `ext`

See `jsroutes-types --help` for more info.

## API

The package exposes a very simple API which the CLI is built on.

The function has the following signature:

```js
function generate(input: string, output: ?string): void;
```

You *must* pass in an `input` location. If you don't pass an output location,
the result will be output to `stdout`.

The function does not return anything;

### Example

```js
const generate = require('jsroutes-types');

generate('/path/to/generated/routes.js', '/path/to/generated/routes.js.flow')
```

## License

Copyright 2018 David Buchan-Swanson

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
