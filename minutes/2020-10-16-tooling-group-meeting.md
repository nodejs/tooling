# Node.js  Tooling Group Meeting 2020-10-16

## Links

* **Recording**:  https://www.youtube.com/watch?v=fCrwd7PVShA&ab_channel=node.js
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/89
* **Minutes Google Doc**: https://docs.google.com/document/d/14i7D32ueFGNb9P7VeTaB0-JWVsCT3ve42rVs1lbBIuA/edit

## Present

* Ian Sutherland (@iansu)
* Wes Todd (@wesleytodd)
* Joe Sepi (@joesepi)



## Agenda

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* recursive filesystem operations api [#78](https://github.com/nodejs/tooling/issues/78)
  * Ian & Joe to work on RFC for copyDir week of the 26th
  * fs.rmdir deprecated in Node 15
  * Added new fs.rm function
    * Some libraries are using fs.rmdir, we should try to get them updated
      * fsextras
      * something else?
      * Make a list (Wes)

* FFI: Foreign Function Interface [#76](https://github.com/nodejs/tooling/issues/76)

* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * Darcy: Nothing new here; would love someone else to pick it up if there's interest; too busy with work work

* ESM module reloading and module graph [#51](https://github.com/nodejs/tooling/issues/51)

* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)

* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)

* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)

* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  * Need to resolve decision to throw or not on argument errors
  * Put up a new PR and see what people think
  * If we can’t reach a decision then involve the TSC
  * Joe is going to resume work on the old PR and address comments
  
* Chat about npm 7

* Chat about fs.promises and missing async methods there
  * Ian will create an issue in tooling repo to start to track any work done there



## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.

