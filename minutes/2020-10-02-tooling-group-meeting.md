# Node.js  Tooling Group Meeting 2020-10-02

## Links

* **Recording**:  https://www.youtube.com/watch?v=4A4_pnghyMw
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/88
* **Minutes Google Doc**: https://docs.google.com/document/d/1aLK-i4zNvaurXih9tcAswC6JfWlwtekJiq-j5xzzPbU/edit

## Present

* Ian Sutherland (@iansu)
* Ruy Adorno (@ruyadorno)
* Joe Sepi (@joesepi)
* Ben Coe (@bcoe)
* Wes Todd (@wesleytodd)


## Agenda

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.
* Ben: action item, we should do a little bit of issue grooming sometime soon.

### nodejs/tooling

* recursive filesystem operations api [#78](https://github.com/nodejs/tooling/issues/78)
   * https://github.com/nodejs/node/pull/35250
   * https://github.com/nodejs/node/pull/35171
   * Ian:
      * a little frustrating that it took us an entire year to get here.
      * Ben: What can we learn.
      * Wes: it’s not the end of the world having a strict and loose API.
* Joe:
    * what were the action items:
      * figure out the API methods that should still be recursive.
      * be open to new methods like cp -R.
* Command Line Argument Parser.
   * it’s been set aside for now.
   * Joe: happy to see it over the finish line.
   * Ben: understands frustration but feels that it’s close.
   * Ruy: start from scratch in terms of PR, but work from Chris’ baseline.

* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)

* FFI: Foreign Function Interface [#76](https://github.com/nodejs/tooling/issues/76)

* DEEP DIVE meeting proposals [#73](https://github.com/nodejs/tooling/issues/73)
  * ESM
    * Tentatively schedule for October 30
  * Roadmap
* ESM module reloading and module graph [#51](https://github.com/nodejs/tooling/issues/51)

* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)

* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)

* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)

* the creeping scourge of tooling config files in project root directories [#79](https://github.com/nodejs/tooling/issues/79)
  * Probably can’t get consensus on a specific config directory
  * Try to encourage projects to make config file locations customizable
  * Reframe this issue
* Becoming a chartered working group
  * Write some kind of charter
  * Roadmap
    * Recursive fs
* pmm
  * Should a working group own this project?
  * Maybe a new working group
  * Definitely some overlap with the Tooling group, but maybe not enough for us to own it


## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.

