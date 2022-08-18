# Node.js  Tooling Group Meeting 2022-08-18

## Links

* **GitHub Issue**: https://github.com/nodejs/tooling/issues/153
* **Minutes Google Doc**: https://docs.google.com/document/d/1ICx74MAnr5ydwyCiQLc7ezeO9pUHNr23IhMyBRM0VJk

## Present

* Tooling team: @nodejs/tooling
* Ruy Adorno: @ruyadorno
* Darcy Clarke: @darcy
* Erick Wendell: @erickwendel_

## Agenda

## Announcements

* Welcome Erick Wendel!

### nodejs/tooling

* @ruyadorno Closed old issues:
  * [distributing CLI tools as self-contained binaries](https://github.com/nodejs/tooling/issues/32) is being followed up by a new [Node.js SEA Team](https://github.com/nodejs/single-executable)
  * [argument parsing](https://github.com/nodejs/tooling/issues/19)
  * [stdin.read interface](https://github.com/nodejs/tooling/issues/68) solved by [Stream consumers API](https://nodejs.org/api/webstreams.html#streamconsumerstextstream)
* Way to extract metadata from package.json of dependency [#150](https://github.com/nodejs/tooling/issues/150)
  * maybe take this out of the agenda until it gets some traction / activity within the tooling group
* Include SemVer in Node.js [#146](https://github.com/nodejs/tooling/issues/146)
  * Darcy wants to chime in
  * Split the cli from the lib codebase
  * Implementation doesn’t need to be node-specific, just plain JavaScript
  * npm cli team will work on a new major version of the semver package to prepare it for being ready to be included in core if we decide to do so
  * semver being added not only to the node runtime but look up to tc39 to the possibility of adding it at a language level, then we can get into browsers an
  * in the short term (next few months) work on cleaning up the current implementation
  * long term, clean up the implementation, make sure it aligns 100% with the spec and than start working with standard bodies to include it in the language
* Regular failures in test-fs-rmdir-recursive on Windows [#132](https://github.com/nodejs/tooling/issues/132)
* Recursive readdir [#130](https://github.com/nodejs/tooling/issues/130)
  * Ethan is waiting on feedback: https://github.com/nodejs/node/pull/41439

## Q&A, Other

## Upcoming Meetings

* **Node.js Project Calendar**: <https://nodejs.org/calendar>

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.

