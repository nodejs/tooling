# Argument Parsing

### Links & Resources

* [Initial Tooling Issue](https://github.com/nodejs/tooling/issues/19)
* [Initial Propoasl](https://github.com/nodejs/node/pull/35015)

----

## `process.mainArgs` Proposal

> Note: This can be moved forward independently of the `util.parseArgs()` proposal/work.
 
### Implementation:

```javascript
process.mainArgs = process.argv.slice(process._exec ? 1 : 2)
```

---

## `util.parseArgs([argv][, options])` Proposal

* `argv` {string[]} (Optional) Array of argument strings; defaults
  to [`process.mainArgs`](process_argv)
* `options` {Object} (Optional) The `options` parameter is an
  object supporting the following properties:
  * `withValue` {string[]} (Optional) An `Array` of argument
    strings which expect a value to be defined in `argv` (see [Options][]
    for details)
  * `multiples` {string[]} (Optional) An `Array` of argument
    strings which, when appearing multiple times in `argv`, will be concatenated 
into an `Array`
  * `short` {Object} (Optional) An `Object` of key, value pairs of strings which map a "short" alias to an argument; When appearing multiples times in `argv`; Respects `withValue` & `multiples`
  * `strict` {Boolean} (Optional) A `Boolean` on wheather or not to throw an error when unknown args are encountered
* Returns: {Object} An object having properties:
  * `args` {Object}, having properties and `Boolean` values corresponding to parsed options passed
  * `values` {Object}, have properties and `String` values corresponding to parsed options passed
  * `positionals` {string[]}, containing [Positionals][]

---

## Examples w/ Output

```js
// default
const argv = ['-f', '--foo=a', '--foo', 'b']
const options = {}
const { args, values, positionals } = parseArgs(argv, options)
args // { f: true, foo: true}
values // { f: [undefined], foo: [undefined] }
positionals // ['b']

// withValue
const argv = ['-f', '--foo=a', '--foo', 'b']
const options = {
    withValue: ['foo']
}
const { args, values, positionals } = parseArgs(argv, options)
args // { f: true, foo: true}
values // { f: [undefined], foo: [undefined,'b'] }
positionals // []

// withValue & multiples
const argv = ['-f', '--foo=a', '--foo', 'b']
const options = {
    withValue: ['foo'],
    multiples: ['foo']
}
const { args, values, positionals } = parseArgs(argv, options)
args // { f: true, foo: true}
values // { f: [undefined], foo: ['a','b'] }
positionals // []

// shorts
const argv = ['-f', '--foo=a', '--foo', 'b']
const options = {
    short: { f: 'foo' }
}
const { args, values, positionals } = parseArgs(argv, options)
args // { foo: true}
values // { foo: [undefined] }
positionals // ['b']
```

### F.A.Qs

- Is `cmd --foo=bar baz` the same as `cmd baz --foo=bar`?
  - Yes, if `withValue: ['foo']`, otherwise no
- Does the parser execute a function?
  - no
- Does the parser execute one of several functions, depending on input?
  - no
- Can subcommands take options that are distinct from the main command?
  - no (this might be a problem? at least it's a more definitive "opinion")
- Does it output generated help when no options match?
  - no
- Does it generated short usage?  Like: `usage: ls [-ABCFGHLOPRSTUWabcdefghiklmnopqrstuwx1] [file ...]`
  - no (no usage/help at all)
- Does the user provide the long usage text?  For each option?  For the whole command?
  - no
- Do subcommands (if implemented) have their own usage output?
  - no
- Does usage print if the user runs `cmd --help`?
  - no
- Does it set `process.exitCode`?
  - no
- Does usage print to stderr or stdout?
  - N/A
- Does it check types?  (Say, specify that an option is a boolean, number, etc.)
  - no
- Can an option have more than one type?  (string or false, for example)
  - no
- Can the user define a type?  (Say, `type: path` to call `path.resolve()` on the argument.)
  - no
- Does a `--foo=0o22` mean 0, 22, 18, or "0o22"?
  - `"0o22"`
- Does it coerce types?
  - no
- Does `--no-foo` coerce to `--foo=false`?  For all flags?  Only boolean flags?
  - no, it sets `{args:{'no-foo': true}}`
- Is `--foo` the same as `--foo=true`?  Only for known booleans?  Only at the end?
  - no, `--foo` is the same as `--foo=`
- Does it read environment variables?  Ie, is `FOO=1 cmd` the same as `cmd --foo=1`?
  - no
- Do unknown arguments raise an error?  Are they parsed?  Are they treated as positional arguments?
  - no, they are parsed, not treated as positionals
- Does `--` signal the end of flags/options?
  - **open question**
  - If `--` signals the end, is `--` included as a positional?  is `program -- foo` the same as `program foo`?  Are both `{positionals:['foo']}`, or is the first one `{positionals:['--', 'foo']}`?
- Does the API specify whether a `--` was present/relevant?
  - no
- Is `-foo` the same as `--foo`?
  - yes <-- ! kind of a blocker for shortopts !
  - Recommend: "No, -foo is shortopts form of --f --o --o" (assuming none are defined, or withValues)
- Is `---foo` the same as `--foo`?
  - no 
  - the first flag would be parsed as `'-foo'`
  - the second flag would be parsed as `'foo'`
- Is `-` a positional? ie, `bash some-test.sh | tap -`
  - no