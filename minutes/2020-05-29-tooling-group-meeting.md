# Node.js Tooling Group Meeting 2020-05-29

## Links

* **Recording**:
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/70
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-05-29-meeting

## Present

* Tooling team: @nodejs/tooling
    * Bryan English (@bengl)
    * Christopher Hiller (@boneskull)
    * Stephen Belanger (@qard)
    * Bradley Farias (@bmeck)
    * Corey Farrell (@coreyfarrell)
    * Ian Sutherland (@iansu)
    * Ben Coe (@bcoe)
    * Ruy Adorno (@ruyadorno)

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.*

## Agenda

* `stdin.read` interface [#68](https://github.com/nodejs/tooling/issues/68)
    * Good to leave the issue open to collect any further feedback but let's take the item out of the agenda
* `fs` hooks [#63](https://github.com/nodejs/tooling/issues/63)
  * vlad had update
  * there's some stuff happening at the same time with Stephen's diagnostic channel work
  * the ESM module loader is being moved off thread, doing so would allow intercepting CJS and collide with this feature
  * also policies is in the same space 
      * https://github.com/nodejs/node/pull/33504
  * follow up: form a meeting for inter-WG modules/security/tooling and other interested parties to discuss overall strategy for these spaces
    * add chris, corey, vladimir, ..
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * Ruy/Ben will prod Darcy
  * still security concerns here 
* ESM module reloading and module graph [#51](https://github.com/nodejs/tooling/issues/51)
  * https://dev.to/giltayar/mock-all-you-want-supporting-es-modules-in-the-testdouble-js-mocking-library-3gh1
  * follow up: go to modules WG with use cases/requirements
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
  * still on Chris' plate who is slacking
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
    * extended on the feature, like I'd (@bcoe) been threatening to: https://github.com/nodejs/node/pull/33491
    * wants to remove experimental flag!
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  * chris  ben ruy to put heads together later
* Ruy: show off npm diff stuff
  * new command arriving soon: `npm diff` (like `git diff`)
  * https://github.com/npm/rfcs/pull/144
* Ben: wants to talk about a thing he has with some interns doing stuff
  * flaky tests!
  * if you have flaky tests let ben know and he will fix them
* meeting format, deep dive
  * Chris open an issue abt what we should deep-dive on

## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


