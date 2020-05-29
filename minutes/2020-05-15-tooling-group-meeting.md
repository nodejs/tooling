# Node.js Tooling Group Meeting 2020-05-15

## Links

* **Recording**: https://youtu.be/UeM3x1_XgoA
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/69
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-05-15-meeting

## Present

* Tooling team: @nodejs/tooling

## Attendance

Benjamin Coe (bcoe)
Ian Sutherland (@iansu)
Christopher Hiller (@boneskull)
Ruy Adorno (@ruyadorno)

## Announcements
 
Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

## Agenda

- `STDIN` https://github.com/nodejs/tooling/issues/68
  - How could reading from `STDIN` be better?
* `fs` hooks [#63](https://github.com/nodejs/tooling/issues/63)
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  - Potential security concerns here
  - Ben would like to better understand the concerns
  - Ongoing discussions of “recursivizing” various APIs
* ESM module graph and unloading ?(??) [#51](https://github.com/nodejs/tooling/issues/51)
  - Weak references might help an implementation
  - https://gist.github.com/tschneidereit/7294906
  - Next steps are to take the requirements to modules WG -- maybe best to join a meeting
  - Ben and chris will join a meeting
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48) (no activity)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
  - Ben: should update the documentation to reflect these new better practices
  - Chris: needs to make list
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
  - Ben: you can turn on source maps programmatically (in a branch)
  - Will only start collecting source maps once you turn it on
  - Chris to comment on pull request, ben to open it
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19) (no activity)



## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


