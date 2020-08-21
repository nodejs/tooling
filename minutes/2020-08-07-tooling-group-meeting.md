# Node.js  Tooling Group Meeting 2020-08-07

## Links

* **Recording**: https://youtu.be/RVSUyInwFOg
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/82
* **Minutes Google Doc**: https://hackmd.io/@nodejs-tooling/2020-08-07-meeting

## Present

* Tooling team: @nodejs/tooling
* Christopher Hiller @boneskull 
* Dominykas Blyžė (@dominykas)
* Ian Sutherland (@iansu)
* Ruy Adorno (@ruyadorno)
* Bryan English (@bengl)
* Wes Todd (@wesleytodd)

## Agenda

## Announcements
 
Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* the creeping scourge of tooling config files in project root directories [#79](https://github.com/nodejs/tooling/issues/79)
  * front page hacker news!!
  * wes: most of the config-loading packages are doing a lot of work
    * they load the files, difft formats, merge files, etc. etc.
    * we do not care about the contents of those files
    * we only care _where_ the files are
    * see https://node-tooling.slack.com/archives/CCB5622HW/p1596823348246000
  * ian: `-c` flag? start using config dir with tools that support an alternative path
  * chris: ask tools to add a `-c` flag
  * wes: the `-c` flag isn't really the way forward
    * we want to move burden off of user
    * ask config file loader projects (?) to use a package which would add `.config` or whatever to the search algorithm
  * dominykas: a new module would have slower traction
    * maybe small PR?? add a path
  * wes: it may not be that easy, some things do weird stuff
* recursive filesystem operations api [#78](https://github.com/nodejs/tooling/issues/78)
  * do the deep dive mtg instead
* FFI: Foreign Function Interface [#76](https://github.com/nodejs/tooling/issues/76)
  * bryan: nothing new, but gus caplan is working on fast api stuff to make this easier
* DEEP DIVE meeting proposals [#73](https://github.com/nodejs/tooling/issues/73)
  * - Chris to schedule deep dive for recursive fs operations
* Recommendation for tooling config file location/format [#71](https://github.com/nodejs/tooling/issues/71)
  * removed from agenda
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * ben: darcy and I did a "spike", but might want to wait on PR until after deep dive
* ESM module reloading and module graph [#51](https://github.com/nodejs/tooling/issues/51)
  * ben: we should pick a problem
    * the proxyquire use-case
  * ben & chris need to attend modules meeting with this use-case
  * 
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
  * we know stephen is working on stuff
  * Ben: we need to ensure stephen understands our use-cases
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
  * ben: remove from agenda(from last meeting)?
  * ian: stack trace interleaves sources and compiled?
  * Ian will try this out and see if it works
  * jordan might be working on standardized stack traces
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  * we need to send a PR
  * todo: chris
  * ben: we need to frame it as something that node would consume in the future

## Q&A, Other

- Ben: look at my PR https://github.com/yargs/yargs-parser/pull/295
  - publishes CJS, ESM and for deno
  - wes: if we had a good set of tools for dual publishing...
    - separate packages, e.g., yargs-mjs and yargs-cjs and yargs-deno who knows
    - npm rfcs for semver dist-tag resolution etc.  (could leverage dist-tags for this problem)
    - wes I wrote a tool internally to do stuff like this
- Ruy: releasing npm v7 beta next week (sshhshhh!~!)
  - `npm i -g npm@next-7`
## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


