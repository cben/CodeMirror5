lib/codemirror.js built from tag `5.65.13` using yarn 1.22.22.

This is primarily useful for including CodeMirror >= 5.20 as a git submodule.
Specifically, submodules work on GitHub Pages.

You don't have to trust my build.  I recommend taking upstream CodeMirror,
running `./build-releases.sh` yourself (latest version in my
`build-releases` branch) and pushing the tags it creates to your own fork.

build output:

```bash
$ yarn install
yarn install v1.22.22
info No lockfile found.
[1/4] Resolving packages...
warning @rollup/plugin-buble > buble > acorn-dynamic-import@4.0.0: This is probably built in to whatever tool you're using. If you still need it... idk
warning @rollup/plugin-buble > @types/buble > magic-string > sourcemap-codec@1.4.8: Please use @jridgewell/sourcemap-codec instead
warning puppeteer@1.20.0: < 22.8.2 is no longer supported
warning puppeteer > rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
warning puppeteer > rimraf > glob@7.2.3: Glob versions prior to v9 are no longer supported
warning puppeteer > rimraf > glob > inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
warning rollup-plugin-copy > globby > glob@7.2.3: Glob versions prior to v9 are no longer supported
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved lockfile.
$ npm run-script build

> codemirror@5.65.13 build
> rollup -c


src/codemirror.js → lib/codemirror.js...
(!) Circular dependencies
src/display/focus.js -> src/display/selection.js -> src/display/focus.js
src/display/highlight_worker.js -> src/display/operations.js -> src/display/scrollbars.js -> src/display/scrolling.js -> src/display/highlight_worker.js
src/display/line_numbers.js -> src/display/update_display.js -> src/display/highlight_worker.js -> src/display/operations.js -> src/display/scrollbars.js -> src/display/scrolling.js -> src/display/line_numbers.js
...and 4 more
created lib/codemirror.js in 584ms

src/addon/runmode/runmode-standalone.js → addon/runmode/runmode-standalone.js...
created addon/runmode/runmode-standalone.js in 32ms

src/addon/runmode/runmode.node.js → addon/runmode/runmode.node.js...
created addon/runmode/runmode.node.js in 29ms
Done in 13.27s.
$ npm list --depth=0
codemirror@5.65.13 /home/beni/MD/mathdown/CodeMirror
├── @rollup/plugin-buble@0.21.3
├── blint@1.1.2
├── cm5-vim@0.0.5
├── node-static@0.7.11
├── puppeteer@1.20.0
├── rollup-plugin-copy@3.5.0
└── rollup@1.32.1

$ npm run build

> codemirror@5.65.13 build
> rollup -c


src/codemirror.js → lib/codemirror.js...
(!) Circular dependencies
src/display/focus.js -> src/display/selection.js -> src/display/focus.js
src/display/highlight_worker.js -> src/display/operations.js -> src/display/scrollbars.js -> src/display/scrolling.js -> src/display/highlight_worker.js
src/display/line_numbers.js -> src/display/update_display.js -> src/display/highlight_worker.js -> src/display/operations.js -> src/display/scrollbars.js -> src/display/scrolling.js -> src/display/line_numbers.js
...and 4 more
created lib/codemirror.js in 599ms

src/addon/runmode/runmode-standalone.js → addon/runmode/runmode-standalone.js...
created addon/runmode/runmode-standalone.js in 33ms

src/addon/runmode/runmode.node.js → addon/runmode/runmode.node.js...
created addon/runmode/runmode.node.js in 32ms
```

----


# CodeMirror

[![Build Status](https://github.com/codemirror/codemirror5/workflows/main/badge.svg)](https://github.com/codemirror/codemirror5/actions)
[![NPM version](https://img.shields.io/npm/v/codemirror.svg)](https://www.npmjs.org/package/codemirror)

CodeMirror is a versatile text editor implemented in JavaScript for
the browser. It is specialized for editing code, and comes with over
100 language modes and various addons that implement more advanced
editing functionality. Every language comes with fully-featured code
and syntax highlighting to help with reading and editing complex code.

A rich programming API and a CSS theming system are available for
customizing CodeMirror to fit your application, and extending it with
new functionality.

You can find more information (and the
[manual](https://codemirror.net/5/doc/manual.html)) on the [project
page](https://codemirror.net/5/). For questions and discussion, use the
[discussion forum](https://discuss.codemirror.net/).

See
[CONTRIBUTING.md](https://github.com/codemirror/CodeMirror/blob/master/CONTRIBUTING.md)
for contributing guidelines.

The CodeMirror community aims to be welcoming to everybody. We use the
[Contributor Covenant
(1.1)](http://contributor-covenant.org/version/1/1/0/) as our code of
conduct.

### Installation

Either get the [zip file](https://codemirror.net/5/codemirror.zip) with
the latest version, or make sure you have [Node](https://nodejs.org/)
installed and run:

    npm install codemirror

**NOTE**: This is the source repository for the library, and not the
distribution channel. Cloning it is not the recommended way to install
the library, and will in fact not work unless you also run the build
step.

### Quickstart

To build the project, make sure you have Node.js installed (at least version 6)
and then `npm install`. To run, just open `index.html` in your
browser (you don't need to run a webserver). Run the tests with `npm test`.
