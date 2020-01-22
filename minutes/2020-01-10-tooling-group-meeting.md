# Node.js Foundation Tooling Group Meeting 2020-01-10

## Links

- **Recording**: none wtf
- **GitHub Issue**: https://github.com/nodejs/tooling/issues/57
- **Minutes Google Doc**: https://docs.google.com/document/d/1QrM2pBeMlkUmG-XYV7pGdcGCYqQXANqQJQTL8pQbTqA/edit

## Present

- Tooling team (@nodejs/tooling)
  - Ian Sutherland (@iansu)
  - Ruy Adorno (@ruyadorno)
  - Christopher Hiller (@boneskull)
  - Bryan English (@bengl)
  - Matan Kushner (@matchai)
  - Corey Farrell (@coreyfarrell)
  - Ben Coe (@bcoe)

## Agenda

## Announcements

Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

- tracking "hot module reloading" for ESM in core [#51](https://github.com/nodejs/tooling/issues/51)

  - Chris: it’s in the spec that we can’t currently hot reload ESM modules; tools need this, but who might have the team to work on it.
  - Ben: we should poke around and see who has a pressing need for this:
  - Chris: haven’t heard anything yet, might be that it’s too soon for folks to know it’s a problem.
  - Ruy: business case is hampered by adoption.
  - Corey: this is an example of spec being written for browser, and security needs that come along with it; this is an example of needing to escape the walled garden.
  - Corey: I wonder if this could be something that also benefits WebDriver; does it have similar needs to escape restrictions.
  - Chris: There’s agreement this is something that’s needed; implementation might be contentious. What we lack is motivation.

- meeting at OpenJSF Summit [#44](https://github.com/nodejs/tooling/issues/44)
  - (Chris summarizes)
  - Chris: if we want to tackle better argument parsing, who’s our audience: are we targeting folks learning Node.js, or folks building libraries?
    - seemed to be consensus we don’t want to target power users.
    - there was a case that not all languages have this ability.
  - Corey: better if the code could work as a foundation, not be just for the simple cases.
  - Matan: for the simplest approach do we want any typing.
  - Chris: we need someone to own this …
  - Chris: self contained binaries
    - it’s nice to be able to distribute a self contained tool that folks don’t need to know specific about.
    - zeit has been doing some work in this area.
    - Ian: one of the former maintainers of create react app works at zeit, I asked him a month ago ot join (everyone is busy, forgot to join).
- A better way to detect a process is exiting [#42](https://github.com/nodejs/tooling/issues/42)
- Source Map V3 Support in Node.js [#40](https://github.com/nodejs/tooling/issues/40)
  - https://github.com/nodejs/node/pull/31132
- argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
  - this was popular idea, and we want to move forward with some sort of solution
  - Ruy will drop the "process.scriptArgs" idea (or whatever it's called; which is just `process.argv.slice(2)`)

## Q&A, Other

Corey: I’m going to be working on the `child_process.spawn()` hook to allow monkeying with the env (for nyc). I've opened an issue in node repo for similar functionality for worker threads

## Upcoming Meetings

- **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.
