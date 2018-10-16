# Node+JS Interactive 2018 Tooling Group Session

First official meeting of the tooling working group, held as part of the 
collaborator summit at Node.js interactive.

Schedule next meting [here](https://github.com/nodejs/tooling/issues/1).

## Attendance

### Chris Hiller (@boneskull):

* works for IBM.
* maintains Mocha.
* conceived of tooling working group as way to better serve Node users 
  writing Command Line Tools; taking into account user feedback.
  
### Ben Coe (@bcoe)

* PM at npm, Inc.
* maintains yargs, Istanbul, standard-version.
* has been working with Christopher and others to beter establish tooling
  working group.
  
### Ian Sutherland (@iansu):

* maintains create-react-app.
* interested in getting involved in tooling working group.

### Guy Bedford (@guybedford)

* contributes to modules working group.
* maintains rollup, systemjs.

### Oktavianus Ludirio (@oludiro)

* works at Zillow.
* interested in learning more about writing tooling in Node.js.

### Daniel Stockman (@evocateur)

* works at Zillow.
* maintains Lerna.

### Erick Wendel (@erickwendel)

* Microsoft MVP.
* curious about tooling (would like to contribute more).

### Ruy Adorno (@ruyadorno):

* contributor to yeoman.

### Michel Lopez (@michellopez):

* senior program manager at Microsoft.
* interested in making sure Node.js/npm are stable on Windows.
* excited that Windows and Linux build times are now equivilent.

### Bryan English (@bengl)

* engineer at Intrinsic.
* interested in intersection between tooling and security (interesting challenges).

## Introduction/Mission

* *Chris*: if you had to write a bundler, or scaffolding tool, how could APIs
  with Node.js make your life easier for you.
  * ran user feedback session that indicated there was room for improvement
    in some APIs.

## Initial Successes

* `mkdirp`:
  * just landed in Node.js core.
  * process of landing was a bit bumpy, due to questions around feature
    detection.
* `readdir`:
  * you can now fetch stat information without crossing the JavaScript C++
    boundary multiple times.
* V8 Coverage:
  * you can now dump coverage information directly from V8.
  
### What We Learned

* *Ben*: we've had some good successes, but we learned there were some
  shortcomings around feature detection -- maybe we need to formalize how we
  propose features to work on ... brings us to.
  
## Backwards Compatibility and Polyfills

* *Chris*:
  * want feature detection in Node.js, but don't want to litigate it right now.
  * for time being, perhaps we can get away with `process.version`.
  * good start would be making pulls to community:
    * update `mkdirp`, `rimraf`, based on `process.version`.
    * _Michel_ also advocates this approach.

* *Daniel*:
  * how do we get adoption if only cutting edge Node.js should be using?
  * perhaps backporting should be goal when possible?

* *Bryan/Chris*:
  * backporting is a pain in the butt, perhaps we just agree to polyfill;
    see: readable stream.

* *Ruy*:
  * there are good aspects to not backporting features, drive more people
    to adopt new Node.js versions.

* *Ian*:
  * because we're targetting CLI tools, perhaps we can be more aggressive
    about pushing people to upgrade to new Node.js:
    
* *Daniel*:
  * on topic of polyfills, `graceful-fs` is an example of 
    _how not to polyfill_.

* *Guy*:
  * fs-extra is a better approach, doesn't mutate global fs object

we seem to have reached relative consensus that:

* we'll shim old library versions.
* won't backport to old Node.js versions.
* will use `process.version` for feature detecton.

## What other sorts of features should we be working on?

* *Chris*:
  * argument parsing could be made better than `process.argv.slice(2)`.

* *Bryan*:
  * would like to see `execvp` implemented, this could be a good alternative
    for how `npx` currently runs.

* *Guy*:
  * look at the libraries that perform Windows shimming (`cross-env`, `cross-spawn`).

* *Ben*:
  * I put together a list of these Windows issues which can be found here:
  * https://github.com/bcoe/awesome-cross-platform-nodejs

* *Chris*:
  * what if we were smarter abut path generation, and `path.separator` was
    no longer a thing you needed to do.

* *Guy*:
  * interesting to note that Deno has a [proposal to use forward-slashes on Windows](https://github.com/denoland/deno/issues/957)
  
* *Daniel*:
  * whatever we build, let's avoid having runtime flags for it, e.g., forward
    slashes being enabled by a flag.

* *Ben*:
  * _let's step up 30,000', and talk about some of the higher level goals of the
    _Tooling Initiative :tm:_.

## Action Items

* *Chris*:
  * let's finish building `rimraf`. (@bcoe, @boneskull).
  * let's get `mkdirp` shimmed (@iansu).
  * let's figure out how we're going to approach getting further user feedback (@bcoe).
  * figure out how we're announcing future meetings; blog post? (@boneskull).

* *Ben*:
  * let's develop a roadmap we can share with TSC and other contributors. (@bcoe).
  * let's schedule our first meeting:
    * figure out roadmap first, use this to drive user feedback work.
  * let's keep Windows folks in the loop, and make reducing Windows friction
    an important initiative of this group (@michellopez)
  * let's chat with TSC and figure out how our group interacts (@bcoe, @boneskull).

* *Guy*:
  * let's reach out to library maintainers, and see how they feel about getting
    their work brought into core (@guybedord).
    * this could be a great way to get more Node contributors; perhaps
      coordinate with Mentorship Group? (CC: @dshaw).

* *Bryan*:
  * let's survey the community (@bengl, @boneskull, @bcoe).
    * this can/should dovetail with community outreach/roadmap work.
  * should we become an officially [chartered group](https://github.com/nodejs/TSC/blob/master/BasePolicies/Charter.md)? (@bengl, @boneskull, @bcoe)
    * what are the advantages, disadvantages?

* *Daniel*:
  * let's start pulling together some documentation describing what tooling
    best practices currently look like in the community (@evocateur).
    * we can evolve this document over time as we land work.
  * in general let's better define the scope of the term tooling (@bengl, @evocateur, @michel, @boneskull):
    * is it command line tools?
    * is it the developer experience around APIs? (_Bryan: does crypto fall under this?_).
    * is it tooling around building Node.js?

* *Michel*:
  * there are new Azure images available we could use for testing,
    let's see if we can get these running for Tooling group (@michellopez).
  * can we get a pre-made Node development [ievm](https://github.com/xdissent/ievms) 
    for this initiative too? (@michellopez).
