# Node.js Tooling Group Meeting 2020-02-21

## Links

* **Recording**: https://youtu.be/b1rthodJAQw
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/61
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-02-21-meeting

## Present

* Tooling team: @nodejs/tooling
* Wes Todd (@wesleytodd)
* Bryan English (@bengl)
* Ian Sutherland (@iansu)
* Ruy Adorno (@ruyadorno)
* Darcy Clarke (@darcy)
* Corey Farrell (@coreyfarrell)
* Christopher Hiller (@boneskull)

## Agenda

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

- Standalone binaries for cli apps etc
  - see https://github.com/nodejs/tooling/issues/32
  - `pkg` is maintained but not actively developed (Zeit not currently dogfooding)
  - `ncc` makes load times fast by shipping a single js file
  - File system hooks (similar to loader hooks) would be nice
  - Possible approach to this problem:
    - Bundle JavaScript into a node binary and change the entrypoint
    - Work with an already bundled app (via something like `ncc`)
    - Work on fs hooking to allow non bundled code to be shipped
    - Add the V8 cache into the binary
    - Slim down the node binary to only the required modules
- `npm` workspaces
  - See RFC issue for latest: https://github.com/npm/rfcs/pull/103 

* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)

## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


