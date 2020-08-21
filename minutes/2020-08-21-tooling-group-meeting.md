# Node.js Tooling Group Meeting 2020-08-21

## Links

* **Recording**: https://youtu.be/wrYh6wdHN5o
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/83
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-08-21-meeting

## Present

* Tooling team: @nodejs/tooling
* Ruy Adorno (@ruyadorno)
* Wes Todd (@wesleytodd)
* Ian Sutherland (@iansu)
* Bryan English (@bengl)


## Agenda

## Announcements
 
Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* the creeping scourge of tooling config files in project root directories [#79](https://github.com/nodejs/tooling/issues/79)
  * Chris: might want to schedule a deep dive for this
* DEEP DIVE meeting proposals [#73](https://github.com/nodejs/tooling/issues/73)
* recursive filesystem operations api [#78](https://github.com/nodejs/tooling/issues/78)
  * Deep dive scheduled for Sep 4 2020 (next meeting)
  * We need to work on an agenda, Chris will come up w/ something
* FFI: Foreign Function Interface [#76](https://github.com/nodejs/tooling/issues/76)
  * no movement
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * make agenda item for the filesystem deep dive
  * darcy did a "spike" w/ Ben on this
  * remember security concerns here
* ESM module reloading and module graph [#51](https://github.com/nodejs/tooling/issues/51)
  * Tweet thread yesterday https://twitter.com/bengl/status/1296513368908587009
    * testdouble has a way to pull this off
    * bryan concerned about putting loaders in a worker thread will break this further
    * we need to understand what testdouble can do and what it can't
    * bradley has aan open PR to run loaders in a worker process (https://github.com/nodejs/node/pull/31229)
    * Chris: need to understand testdouble and take the use-case to the module meeting
    * Bryan: multiple loader PR https://github.com/nodejs/node/pull/33812
    * Ben: libraries using require.extensions seem to be able to resolve problems in userland. it is not as bad as a problem as it theoretically could be
      * see https://www.npmjs.com/package/pirates
    * what happens w/ source maps when used with loaders?
    * Bradley: somebody wrote (Rich?) a loader that allows composition of an array of loaders
      * multiple loader support in core would mean you cannot enforce the "bottleneck" loader
      * Ben: no enforcement in community--`pirates` is opt-in
    * Bradley: proposing a "source map" field returned from loader might work (but not for everything)
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
  * Action item: talk to Stephen about our use-case(s) here (@bcoe)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
  * Ben: joyee implemented something good for "writing coverage" use-case
  * there may be an opportunity to hook into this from user code, but rn it is lowlevel
  * @bcoe will paste an issue number/PR here
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
  * interleaved stack traces
  * using V8's source map field
  * wes/jordan standardizing stack traces? TC39
  * still marked experimental
  * Ian: wrap up these edge cases and remove experimental?
  * Ben: are we ok with format and _not_ using V8's functionality right now?
  * Chris: ask StrongLoop to try native source maps
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  * Chris to send PR




## Q&A, Other
- Ben: I made yargs work in Deno/ESM:
    - https://github.com/yargs/yargs/pull/1708
- Bradley: policies will be moving towards unflagging in next year
  - scoping mechanism will land on `master` on monday
  - "a human might be able to write a policy file"

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


