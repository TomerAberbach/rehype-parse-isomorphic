<h1 align="center">
  rehype-parse-isomorphic
</h1>

<div align="center">
  <a href="https://npmjs.org/package/rehype-parse-isomorphic">
    <img src="https://badgen.net/npm/v/rehype-parse-isomorphic" alt="version" />
  </a>
  <a href="https://github.com/TomerAberbach/rehype-parse-isomorphic/actions">
    <img src="https://github.com/TomerAberbach/rehype-parse-isomorphic/workflows/CI/badge.svg" alt="CI" />
  </a>
  <a href="https://unpkg.com/rehype-parse-isomorphic/dist/index.min.js">
    <img src="https://deno.bundlejs.com/?q=rehype-parse-isomorphic&badge" alt="gzip size" />
  </a>
  <a href="https://unpkg.com/rehype-parse-isomorphic/dist/index.min.js">
    <img src="https://deno.bundlejs.com/?q=rehype-parse-isomorphic&config={%22compression%22:{%22type%22:%22brotli%22}}&badge" alt="brotli size" />
  </a>
</div>

<div align="center">
  A module that exports <a href="https://github.com/rehypejs/rehype/tree/main/packages/rehype-parse"><code>rehype-parse</code></a> for Node.js and <a href="https://github.com/rehypejs/rehype-dom/tree/main/packages/rehype-dom-parse"><code>rehype-dom-parse</code></a> for the browser.
</div>

## Install

```sh
$ npm i rehype-parse-isomorphic
```

## Usage

Use just like
[`rehype-parse`](https://github.com/rehypejs/rehype/tree/main/packages/rehype-parse)
and
[`rehype-dom-parse`](https://github.com/rehypejs/rehype-dom/tree/main/packages/rehype-dom-parse).

> WARNING: The two libraries do not have exactly the same options. Make sure you
> account for the differences when the library is used in Node.js vs the
> browser.

## Why?

It's better to use `rehype-dom-parse` than `rehype-parse` in the browser because
the former has a significantly smaller bundle size
([~8 kB](https://bundlejs.com/?bundle&q=rehype-dom-parse) vs
[~63 kB](https://bundlejs.com/?bundle&q=rehype-parse)).

Typically it's possible to just import `rehype-parse` in Node.js and
`rehype-dom-parse` in the browser, but not always. Sometimes you want to parse
HTML in code that can be used in either the browser or Node.js (i.e. in
[isomorphic code](https://en.wikipedia.org/wiki/Isomorphic_JavaScript)). Which
library would you import in that code?

Without this module you'd be forced to import the lowest common denominator, the
library that works in both Node.js and the browser, which would be
`rehype-parse`. And now your browser JavaScript bundle is ~55 kB bigger than it
should have been! With this module, you use the right library in each
environment.

## Contributing

Stars are always welcome!

For bugs and feature requests,
[please create an issue](https://github.com/TomerAberbach/rehype-parse-isomorphic/issues/new).

For pull requests, please read the
[contributing guidelines](https://github.com/TomerAberbach/rehype-parse-isomorphic/blob/main/contributing.md).

## License

[Apache License 2.0](https://github.com/TomerAberbach/rehype-parse-isomorphic/blob/main/license)

This is not an official Google product.
