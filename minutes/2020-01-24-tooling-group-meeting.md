# Node.js Tooling Group Meeting 2020-01-24

## Links

* **Recording**: https://youtu.be/371RnCGx1Y8
* **GitHub Issue**: https://github.com/nodejs/tooling/
* **Minutes Google Doc**: https://github.com/nodejs/tooling/issues/58

## Present

* Tooling team: @nodejs/tooling
* Wes Todd (@welseytodd)
* Ruy Adorno (@ruyadorno)
* Benjamin Coe (@bcoe)
* Christopher Hiller (@boneskull)

## Agenda

## Announcements
 
Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

- execvp	
  - Wes asking about process replacements; talks about Netflix use case
  - Wants to see Bryan’s PoC if one exists
  - Import maps
  - There is contention (someone paste url to issue)

* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
  - Action item: @boneskull follow up with @bengl

- Issue 44 (followup after summit meeting)
  - Action item: Should be closed

* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
  * corey should do ref impl but he is not present
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
  * we have it but community doesn’t know
  * we need to promote it
  * need an example: https://github.com/bcoe/express-ts-errors 
  * ben wants to write an “official” article about it, introducing to  community, to get feedback, etc.
  * Example of blog post: https://github.com/nodejs/package-maintenance/pull/260

* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  - Ben willing to do a hacking session with Ruy on it
  - This is “rad”
* Support for hooking spawn / spawnSync without patching [#48](https://github.com/nodejs/tooling/issues/48)
  - Ben: I have sticky env var in place for coverage (was part of PR) to allow for coverage on child processes
  - Need to make this available for userland
  - https://github.com/nodejs/node/blob/master/lib/child_process.js#L515
* some bugs found with `mkdir` recursive: 
  * https://github.com/nodejs/node/issues/31481

- Ruy is working on npm “workspaces”
  - Sourcing ideas
  - In design phase
  - This is like from yarn, some stuff from lerna




## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


