# Node.js  Tooling Group Meeting 2022-09-01

## Links

* **Recording**: https://youtu.be/8_ntlIHnErA
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/155
* **Minutes Google Doc**: https://docs.google.com/document/d/11dOy0hFbn2r8nMaSzKomXPoUJIs2XNfUPqoZZk-LhCM

## Present

* Tooling team: @nodejs/tooling
* Ben Coe (@bcoe)
* Erick Wendell (@erickwendel_)
* Ruy Adorno (@ruyadorno)

## Agenda

### nodejs/tooling

* Promisifying modules [#44250](https://github.com/nodejs/node/pull/44250)
  * Confusing to users to have the prefix be required for only the `/promises` implementation
  * We should have the TSC vote one: If we're adding a /promises option to an existing module (e.g., inspector, dns), the the non "node:" import will work, along with the "node:dns/promises" import.
* Way to extract metadata from package.json of dependency [#150](https://github.com/nodejs/tooling/issues/150):
  * AI point Daniel towards existing work.
* Include SemVer in Node.js [#146](https://github.com/nodejs/tooling/issues/146)
  * Standardization of the spec itself is different than the standardization of the implementation
  * Are there usecases for semver in the browser? Otherwise it would be hard to find a place for it on W3C / TC39
* Regular failures in test-fs-rmdir-recursive on Windows [#132](https://github.com/nodejs/tooling/issues/132)
* Recursive readdir [#130](https://github.com/nodejs/tooling/issues/130):
* https://github.com/nodejs/node/pull/41439
* Take a look at https://github.com/nodejs/node/blob/9e98797f44664eb264fa8f67500908824d4aec25/lib/internal/fs/dir.js#L130


* parsArgs update:
  * https://github.com/pkgjs/parseargs/issues
  * https://2ality.com/2022/08/node-util-parseargs.html

## Upcoming Meetings

* **Node.js Project Calendar**: <https://nodejs.org/calendar>

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.

