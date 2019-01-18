# Node.js Foundation Tooling Group Meeting 2019-01-15

## Links

- **Recording**: https://youtu.be/Wq4VU3wo1ag
- **GitHub Issue**: https://github.com/nodejs/tooling/issues/14
- **Minutes Google Doc**: https://docs.google.com/document/d/1MFm0NIkwzQWi5yIEPfDRFcojua2fV7kVv7Jn_c0i0g4/edit

## Present

- Tooling team: @nodejs/tooling
  - Refael Ackermann (@refack)
  - Christopher Hiller (@boneskull)
  - Ian Sutherland (@iansu)
  - Ben Coe (@bcoe)
  - Guy Bedford (@guybedford)
  - Ruy Adorno (@ruyadorno)

## Agenda

- rimraf progress [#13](https://github.com/nodejs/tooling/issues/13)
  - is the annoyance of writing it in C++ worth it? The serial performance is similar to userland.
  - still belongs in core, but not expecting a huge explosion of awesome performance.
  - build wg wants to enable C++ stdlib calls which would potentially provide `rm -rf` functionality -- might be a way to get a performant, low-level implementation
  - may see portability issues (specifically IBM)
- user-land shims for tooling group initiatives [#7](https://github.com/nodejs/tooling/issues/7)
  - Ben reached out to substack and he was “not too jazzed” about switching to a native implementation.
  - make-dir uses node.js native impl https://www.npmjs.com/package/make-dir of mkdirp
  - use @nodejs namespace on npm?
  - github org? We have process.allowedNodeEnvironmentFlags shim available which could move
  - talk to package-maintenance group (@boneskull)
  - Refael: pull parts of chokidar and fs-events into core
  - Refael: we haven’t mapped the gaps in fs.watch. There’s FUD about using fs.watch -- many reach for chokidar/fs-events before trying fs.watch because they know it’s not going to work for them
  - Guy: example of fs.watch being bad: in rollup we use fs.watch but we have to watch many single files instead of directories. Does not scale
  - Guy: maybe some brain drain around understanding of current problems
  - https://mobile.twitter.com/leichtgewicht/status/1073490121737945088
  - cross-spawn and fs.watch/chokidar etc might be more impactful than rimraf
  - Refael: solving cross-spawn may be libuv-related
  - we need a windows person. (@From_Michel)
  - create issue(s) in node core? (@boneskull wouldn’t do this, would write up or tweet or otherwise promote the ideas; ultimately we need to send PRs)
- meeting cadence [#10](https://github.com/nodejs/tooling/issues/10)
  - can we do two youtube streams at once? Ughhhhh @boneskull will follow up
  - currently meeting every 3 weeks but would like 2; this conflicts with benchmarking wg
- TC39 feedback [#11](https://github.com/nodejs/tooling/issues/11)
  - try to get @littledan in attendance in meeting
  - unclear what tooling group relationship will be to language standards, but would like to explore
- update about test coverage in Node.js core: https://github.com/nodejs/node/pull/25157

## Announcements

Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

- rimraf progress [#13](https://github.com/nodejs/tooling/issues/13)
- user-land shims for tooling group initiatives [#7](https://github.com/nodejs/tooling/issues/7)
- meeting cadence [#10](https://github.com/nodejs/tooling/issues/10)
- TC39 feedback [#11](https://github.com/nodejs/tooling/issues/11)

## Q&A, Other

## Upcoming Meetings

- **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.
