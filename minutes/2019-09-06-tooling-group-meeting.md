# Node.js Foundation Tooling Group Meeting 2019-09-06

## Links

- **Recording**:
- **GitHub Issue**: https://github.com/nodejs/tooling/issues/39
- **Minutes Google Doc**: https://docs.google.com/document/d/1yTzQJd2lzse1QWCycjkgosvuyxfHNXogIw73aeSKPSg/edit

## Present

- Tooling team: @nodejs/tooling
- Christopher Hiller (@boneskull)
- Ian Sutherland (@iansu)
- Benjamin Coe (@bcoe)
- Corey Farrell (@coreyfarrell)

## Agenda

## Announcements

*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/tooling

- glob support in core [#38](https://github.com/nodejs/tooling/issues/38)
- new meeting time needed [#36](https://github.com/nodejs/tooling/issues/36)
- distributing CLI tools as self-contained binaries [#32](https://github.com/nodejs/tooling/issues/32)
- Implement shutil in Node.js core [#23](https://github.com/nodejs/tooling/issues/23)
- argument parsing [#19](https://github.com/nodejs/tooling/issues/19)
- Source-Map Support in Node.js: [nodejs/node#28960](https://github.com/nodejs/node/pull/28960/files)

#### Meeting Times

New meeting time: every other Friday at 10a pacific

#### Glob

Corey:
- globbing (e.g. [glob](https://npm.im/glob)) vs [minimatch](https://npm.im/minimatch)
- *Both* should be in core
- Must use the same matching
- Globbing would be useless for nyc w/o minimatch implemntation available

Chris:
- something like `path.match()` for minimatch
- Minimatch and [micromatch](https://npm.im/micromatch)? Analyze the intersection.
- Let's start with `path.match()`

Corey:
- What differences can be eliminated thru options?
- Would be good to coordinate w/ those maintainers to see if they are interested in aligning with nodejs or polyfilling
- Also: ability to replicate functionality of gitignore

#### Source maps

Ben talked about sourcemap support: https://github.com/nodejs/node/pull/28960/files

#### Arg Parsing

We still want to do this, but need time.

@boneskull won't have any time until late October.

- Action item: @boneskull, @iansu - look into micromatch, minimatch, bash and gitignore and compare
- Action item: @nodejs/tooling Review source maps PR https://github.com/nodejs/node/pull/28960
- Action item: @boneskull remove shutil from tooling-agenda
- Action item: @nodejs/tooling reach out to let people know about new meeting times

## Q&A, Other

## Upcoming Meetings

- **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.
