# Node.js Tooling Group Meeting 2020-02-07

## Links

* **Recording**: https://youtu.be/mj33ibz7Ias
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/60
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-02-07-meeting

## Present

* Tooling team: @nodejs/tooling
* Ian Sutherland: @iansu
* Christopher Hiller @boneskull
* Benjamin Coe: @bcoe

## Agenda

## Announcements
 
Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)

  * Implementation should probably be in JS until somebody needs c++ perf
  * C++ impl will be hairy
* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
  * (no activity)
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48) 
  * (no activity)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42) 
  * (no activity)
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40):
  * Ben: haven’t figured out who to talk to about a blog post yet. 
  * If dev.to talk to @boneskull about posting

* argument parsing [#19](https://github.com/nodejs/tooling/issues/19) 
  * ben to create a meeting to brainstorm this thing

* mkdir recursive returns first folder created; see https://github.com/nodejs/node/pull/31530

- Somebody (anybody) research why you can’t pass owner/group to all of these fs functions
  - Libuv does not take ownership/group ?
  - Ask isaac what he is doing with recursive chmod

## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


