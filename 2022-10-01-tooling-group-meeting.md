# Node.js  Tooling Group Meeting 2022-10-01

## Links

* **GitHub Issue**: https://github.com/nodejs/tooling/issues/161
* **Minutes Google Doc**: https://docs.google.com/document/d/1bnMxqJXftu_w3kOkeFSJhCLu4yHdxpJzyQSH-nq0HSE

## Present

* Tooling team: @nodejs/tooling
* Tony Gorez: @tony-go
* Ruy Adorno: @ruyadorno
* Orta: @orta
* Ethan Arrowood: @ArrowoodTech
* Michaël Zasso: @targos89
* Tierney Cyren: @bitandbang

## Agenda

### TypeScript in node
* Group was formed in the last collaborator summit in Austin 2022
* Goal was to just execute TypeScript, no type checks
* Deno rolled back support to type check, it’s a can of worms
* What gets us there
* Pros:
  * Supporting the language that has the largest activity in GitHub
* There’s a lot of ways of taking a TypeScript file and turning it into JavaScript, swc, tsc, etc
* That’s the loaders API
* We don’t want to support TypeScript we want to support people to use TypeScript
* TypeScript needs to be pinned to the local project version
* Build a system that can hook a standard TypeScript loader when trying to run a .ts file
* Transpile files incrementally, similar to how ts-node works
* We have the TypeScript group, Tooling Group, Loading Working Group how can we get all these collaborators together
* Are we only missing the bit in which we can automatically hook a `.ts` file to the typescript loader?
* We need a ts-config in order to properly setup the typescript transpiler
* We need to define a clear line on what gets supported, compare TypeScript support to others such as CoffeeScript, JSX
* We might have touched on a lot of subjects the other working groups are already working on, it would be great to sync back with the Loaders working group on these issues.
* Propose to the typescript team that we build in support to the Node.js loader syntax directly into the package
* From the Node.js side of things we just need to bind `.ts` files to automatically use the typescript loader

### Vendoring packages in core
* Semver is a widely used dependency
* Super stable API
* It’s already bundled in Node.js


## Q&A, Other

## Upcoming Meetings

* **Node.js Project Calendar**: <https://nodejs.org/calendar>

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


