# Implement Recursive Filesystem Operations

> "mkdirp" and "rimraf"

<!-- TOC depthFrom:2 -->

- [Summary](#summary)
- [Motivation](#motivation)
- [Example 1: The Bundler](#example-1-the-bundler)
- [Example 2: The Test Case](#example-2-the-test-case)
- [Notes](#notes)

<!-- /TOC -->

## Summary

Two (2) filesystem operations should be added to Node.js Core:

1. Recursively create a directory (e.g., `mkdir -p foo/bar`)
2. Recursively remove a directory (e.g., `rm -rf foo`)

The popular userland modules [mkdirp](https://npm.im/mkdirp) and [rimraf](https://npm.im/rimraf) respectively provide this functionality.

## Motivation

Keeping Node.js' core API small is a commendable goal.  Additions to Node.js' core API should not be taken lightly!  Yet over time, Node.js' users have found some functionality that truly seems "missing".  **These two operations are frequently-cited examples of userland modules which should be built-in to Node.js core.**

Use cases are *extremely common*, especially amongst Node.js CLI applications.  From bundlers to scaffolding tools to package managers; many need to recursively create and destroy directory structures.  It's inconvenient for users, as many new to Node.js expect this functionality to be part of the "standard library".  New and experienced Node.js users are incredulous that external modules must be installed to do these common tasks.

## Example 1: The Bundler

It's 2018, and developer P.J. needs to bundle a web application.  P.J. has written a bundling tool, `wabpeck`, written in Node.js.  `wabpeck` allows the user to configure an "output" directory using the command-line option, `--output <dir>`.

P.J. chooses the output directory, and runs `wabpeck input.js --output /var/www/sites/pj/staging/alpha/static/dist`.  `wabpeck` fails:

```plain
fs.js:143
    throw err;
    ^

Error: ENOENT: no such file or directory, mkdir '/var/www/sites/pj/staging/alpha/static/dist'
    at Object.fs.mkdirSync (fs.js:872:3)
```

P.J. is confused.  P.J. thinks, "Of course it doesn't exist--why do you think I'm trying to create it?!"  P.J. investigates further, and by random chance, chooses to list the contents of `/var/www/sites/pj/staging/alpha`:

```plain
total 16
-rw-r--r--  1 pj        wheel  5979 Jun  8 11:01 anarchist_cookbook.txt
```

P.J. (somehow) realizes that `/var/www/sites/pj/staging/alpha/static` doesn't exist, so `fs.mkdirSync` can't create `/var/www/sites/pj/staging/alpha/static/dist`.

Because `fs` contains no functionality to do this, P.J. now has two choices: modify `wabpeck` to use [mkdirp](https://npm.im/mkdirp), or re-invent a wheel.

## Example 2: The Test Case

P.J. has made the change to use [mkdirp](https://npm.im/mkdirp), but wants to ensure it's correct.  Like a good developer, P.J. writes an integration test, careful to clean up afterwards:

```js
const {tmpdir} = require('os');
const {join} = require('path');
const {existsSync, rmdirSync} = require('fs');
const assert = require('assert');

describe('--output', function() {
  it('should create a directory recursively', function() {
    const recursive1dir = join(tmpdir(), 'recursive-1');
    const recursive2dir = join(recursive1dir, 'recursive-2');
    // minified dummy output bundle
    const expected = join(recursive2dir, 'input-fixture.min.js');
    const w = wabpeck({
      input: join(__dirname, 'input-fixture.js') // dummy input file
      output: recursive2dir
    });
    try {
      w.bundle();
      assert.ok(existsSync(expected));
    } finally {
      rmdirSync(recursive1dir);
    }
  });
});
```

Accidentally practicing TDD, P.J. runs the test and notes it's throwing an exception on the call to `rmdirSync`.  

P.J. realizes `rmdirSync` fails for a similar reason; `recursive1dir` isn't empty.  Again, P.J. has two choices: modify the tests to use [rimraf](https://npm.im/rimraf), or re-invent another wheel.

## Notes

Assuming methods would be added to `fs`, this would not (as far as the author knows) require breaking changes which would violate the `fs` module's "Stable" stability status.

There is precedent for these out-of-the-box in other languages, such as Python (`os.makedirs()` and `shutil.rmtree()`).
