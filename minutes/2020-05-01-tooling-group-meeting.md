# Node.js  Tooling Group Meeting 2020-05-01

## Links

* **Recording**:  https://www.youtube.com/watch?v=zIa-_nAlZts
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/67
* **Minutes Google Doc**: https://docs.google.com/document/d/1mBz6dXZADs3vEZMqJP1kk_TjqNSvenLfH4UgVokDDwo/edit

## Present

* Tooling team: @nodejs/tooling
* Christopher Hiller @boneskull
* Ian Sutherland @iansu
* Ruy Adorno @ruyadorno
* Anton Korzunov @thekashey
* Darcy Clarke @darcyclarke

## Agenda

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
	* react hot loader
	* it’s harder to do hot module reloading w/ ESM in node.js
	* not so bad in the browser
	* two APIs needed
		* some module wants to know who called it (parent module)
		* destroy the whole tree of modules, optional target (destroy modules “in direction” of another module)
	* action item: @boneskull will write this up
	
* `fs` hooks [#63](https://github.com/nodejs/tooling/issues/63)
	* follow up with vladimir about his...thing with the hooks

* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
	* darcy ready to sync up on this

* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
	* action item: @boneskull go review notes and see what needs to be done
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
	* people want it to be “stable” not “experimental” as per some twitter thread
	* ben: maybe keep it behind a flag??
	* but otherwise there are no big issues
	* programmatically enable, but also a disclaimer
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)

## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


