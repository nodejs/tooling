# Node.js  Tooling Group Meeting 2020-03-06

## Links

* **Recording**: https://youtu.be/NSowmWnKuyE
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/62
* **Minutes Google Doc**: https://hackmd.io/@boneskull/nodejs-tooling-group-2020-03-06

## Present

* Tooling team: @nodejs/tooling
* Christopher Hiller: @boneskull
* Ruy Adorno: @ruyadorno
* Corey Farrell @coreyfarrell
* Ian Sutherland: @iansu
* Ben Coe [@BenjaminCoe](https://twitter.com/BenjaminCoe)
* Darcy Clarke: @darcyclarke
* Bryan English: @bengl


## Agenda

## Announcements
 
*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

* `fs` hooks [#63](https://github.com/nodejs/tooling/issues/63):
    * proposing a shim layer for `fs`, to make it easier to write tools that hook in to the file-system.
    * Corey: re ESM loader hooks; there's an experimental flag. use babel-plugin-istanbul to get coverage of natively-loaded ESM
    * Wes: tink/pnp is top-of-mind, but this sort of thing will serve many more purposes than just this
    * Corey: if you need real security look to the operating system; we need to be careful about overselling what this sort of thing can lock down
    * there's a feeling we want to wait for import maps / loader hooks?
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * Ben: maybe a good place to get involved for someone who wants to start contributing to the node project
* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
  * Ben: we should talk to TSC about many overlapping concerns regarding filesystems
* Support for hooking spawn / spawnSync **without patching**. [#48](https://github.com/nodejs/tooling/issues/48)
  * Corey: remove agenda tag for now
  * Ben: let's keep this and #42 tagged
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40):
    * I wrote a blog post:  [Source Maps in Node.js](https://medium.com/@nodejs/source-maps-in-node-js-482872b56116)
      * Chris: syndicate this content!!!! to dev.to
    * Next steps for the API?
    * _Adding_ source maps? for Jest
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  * we kicked a few things out
  * points of contention:
    * single-dash flags, what does `-abc` do
    * we should do some usability tests: ask people who haven't built command-line tools (yet) if the API makes sense and what they expect it to do?  ideally someone with CLI experience.
    * Corey: will want to see a proof-of-concept implementation

## Q&A, Other

## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


