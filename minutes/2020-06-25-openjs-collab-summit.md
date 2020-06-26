# Node.js Tooling Group Collaboration Session at OpenJS Collaborator's Summit, June 25th 2020

Tracking issue: https://github.com/nodejs/tooling/issues/74

## Participants
- Christopher Hiller (@boneskull)
- Benjamin Coe (@bcoe)
- Bryan English (@bengl)
- Tobias Koppers (@sokra)
- Trivikram Kamat (@trivikr)
- Dominykas Blyžė (@dominykas)
- Ian Sutherland (@iansu)
- Joe Sepi (@joesepi)
- Richard Lau (@richardlau)
- Ruy Adorno (@ruyadorno)
- Darcy Clarke (@darcyclarke)
- Jan Krems
- Stephen Belanger (@qard)
- Michael Dawson (@mhdawson)
- Ruben Bridgewater (@BridgeAR)
- Benjamin Gruenbaum (@benjamingr)

## Agenda Voting

We voted on these topics (as per the _x_'s).

- Potential topics of conversation (let’s pick 2 or 3 to discuss):
  - ffi (foreign function interface) _xxx_
  - Command line parsing. _xxxxx_
  - `package.json` scripts with node (e.g., `node --require-module=rmdir -rf foo.js`). _xxxxx_
  - Flaky test tracking?
  - `execvp` _x_
  - V8 caching for startup performance _xx_
  - `cpFile` (copy recursive). _xxxx_
  - [Recommendation for tooling config file location/format](https://github.com/nodejs/tooling/issues/71) _xx_

## Agenda

- Mission statement (what the heck is the tooling group?).
- npm scripts with node.
- command line parsing.
- cpFile.

## Notes

- Ben gives intro to group mission
- We take votes for topics

### Builtin node scripts, e.g., node --require-module=rmdir -rf foo.js

Ian: how would this work?

Chris: Node.js ships with some lightweight executable scripts that wrap useful builtin functions, e.g., rmdir mkdir
  - For portability
  - This is package-manager independent

Tobias: you could use `node -e \”fs.rmdir()\”`

Ben: `node -e` is gross

Ian: I still use userland rimraf because I need the binlink even though it’s available in fs with recursive option.  Seems silly

Ben: good for those new to Node.js
  - having to hunt  down which 3p module to bring in is painful.  There are many for any given task

Tobias: a standard interface for calling a node builtin function with a syntax for specifying arguments

Bryan gives example: `node -c fs mkdir recursive:true /foo/bar/mydir`
  - POC: https://gist.github.com/dominykas/396b3279eceb3ad5ffeddacf30fd35e7
  - ./xnif.js fs.mkdir ./new/dir --recursive=true

Ian/Ben: ties into command-line argument parsing; if we had the arg parser it’d help get this done

Tobias: this would be useful because I am a Windows user and people put linux nonsense in the `package.json` scripts

### Argument parsing

Ben: a minimal command-line argument parser
  - Chris’ example implementation https://github.com/boneskull/dead-simple-testing-with-mocha/blob/master/03-actual-tests/bargs/src/index.js
  - Dominykas another example: https://gist.github.com/dominykas/396b3279eceb3ad5ffeddacf30fd35e7 (this is for executing node internal functions - argument parsing here is made up on the fly)

(comment): There are many different ways to parse arguments, there’s no standard, etc.

Chris: There’s a set of features common to most every command-line tool in the node ecosystem; this common set is what we focus on
  - Examples of usage: https://speakerdeck.com/boneskull/dead-simple-testing-with-mocha?slide=32

### cpFile

Ian: we have made some other fs functions “recursive” e.g., mkdir and rmdir, but being able to copy a file tree would be great

Bryan: might be tricky since fs.cpFile does not take an option. Maybe new function?

### FFI (Foreign Function Interface)

Bryan: there’s a lot of options for including native code in Node.js.  NAPI, old style. 
  - There’s overhead; you have to convert from C++ objects to JS objects and back
  - FFI would allow calling of native code from Node.js without a custom C++ wrapper
  - There’s even more overhead here (performance?)
  - New feature in V8: “fast api calls”
  - There’s an open (?) PR to consume this to call hrtime which improves perf
  - Do we want an FFI available in Node?
  
Michael: we discussed FFI during NAPI effort
  - We believed that FFI would be useful, but it never got done
  - It allows more interactivity with javascript
  - May be easier to use for developers

Bryan: when you provide a function to the V8 “fast api calls” api you must provide the “fast” implementation and the “slow” implementation as well. You don’t get it for free
  - Node provides access to the API, hopefully to avoid the “slow” implementation

Michael: can we make an API that auto-generates code and makes the adapter for you

Bryan: here are some experiments on this front: https://github.com/bengl/sbffi (the tcc branch is the closest to what I’m proposing, but the shared buffer part isn’t important)

Ben: we should get this on the agenda

Michael: may want to pull some NAPI team members

### Action Items

- Ian: make issue for cpFile
- Bryan: upsert an issue for FFI (including concrete use cases, etc.)
- Chris: import this doc into meeting minutes
- Darcy: when you should schedule these hacking sessions?
- Ben: my weeks tend to free up a bit on Thursdays and Fridays (could have my arm twisted into a Saturday, but this might limit people).

**We have a meeting every two weeks, please join: https://github.com/nodejs/tooling**
