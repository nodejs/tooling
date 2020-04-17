# Node.js  Tooling Group Meeting 2020-04-17

## Links

* **Recording**:
* **GitHub Issue**: https://github.com/nodejs/tooling/issues/66
* **Minutes Doc**: https://hackmd.io/@nodejs-tooling/2020-04-17-meeting

## Present

* Tooling team: @nodejs/tooling
* Christopher Hiller (@boneskull)
* Darcy Clarke (@darcyclarke)
* Ruy Adorno (@ruyadorno)
* Vladimir de Turckheim (@vdeturckheim)
* Ian Sutherland (@iansu)
* Stephen Belanger (@qard)
* Wes Todd (@wesleytodd)
* Corey Farrell (@coreyfarrell)
* Bryan English (@bengl)
* Ben Coe (@bcoe)

## Agenda

### Announcements

* I wrote a blog post on [how maintainers should think about Node versions](https://openjsf.org/blog/2020/04/16/maintainers-should-consider-following-node-js-release-schedule/).

### nodejs/tooling

> Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

* audit hooks and fs hooks
  * "audit hooks":  https://github.com/nodejs/security-wg/issues/626
    * Vladimir: MS wanted auditing hooks in Node.js
    * ability to register "hooks" for particular events
    * syscalls (fs access, etc)
    * hooks for some JS primitives including `eval` and `Function` (security-related)
    * working on PoC
    * many "hooks" are being added to Node.js, or want to be added
    * _should we have a unified interface for instrumenting Node.js?_ whether for security or an `fs`-hooks-like API?  can we make `fs` "lie" or otherwise (this is just one use case)?
    * akin to Java's javaagent (?) flag 
    * hope to avoid multiple libraries doing their own instrumentation/monkeypatching/etc
    * similar efforts: @bengl with the fs hooks, stephen belanger with diagnostic "metadata" channel
    * we need some way to control the behavior of the hook (read-only?) and sync/async hooks
    * Twitch stream https://www.twitch.tv/ecares
  * `fs` hooks [#63](https://github.com/nodejs/tooling/issues/63)
    * if async hooks can do what this can do, then we can drop this impl
    * we need a way of blocking calls, mutating arguments, and providing completely different return values
* chmod -R [#59](https://github.com/nodejs/tooling/issues/59)
  * Darcy still may get involved
  * Ben offers assistance
  * Darcy appreciates it
  * Follow up actions added to issue
* tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)
  * Corey: in v14.0.0, experimental modules warning is squelched
  * Ruy: let's rename this issue to "unloading modules in ESM"
  * [Loader hooks presentation from Vlad at NJSI2019]( https://static.sched.com/hosted_files/njsi2019/ed/loader_hooks.pdf)
  * action item for Chris, talk to @theKashey of `rewiremock` and `proxyquire` about needs
* Support for hooking spawn / spawnSync without patching. [#48](https://github.com/nodejs/tooling/issues/48)
  * falls into "audit hooks" bucket, but needs to manipulate arguments.
  * action item for somebody: link this issue to @ecares
* A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
  * "unified process exiting event" (almost everything except `SIGKILL` and.... core dumps)
  * `signal-exit` essentially
      * https://www.npmjs.com/package/signal-exit
  * needs a PR at this point
  * process.on('real-exit')
* Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
* argument parsing [#19](https://github.com/nodejs/tooling/issues/19)

### Q&A, Other

* Ben: https://github.com/googleapis/release-please
* Corey: wants to allow only the bot to publish a package (roles/perms) on npm
* Darcy: scoped auth tokens? token for publishing a particular package. needs RFC!
* Ruy: go to `#npm` in https://node-tooling.slack.com for discussion


## Upcoming Meetings

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


