# Node.js Foundation Tooling Group Meeting @ OpenJS Foundation Collab Summit, May 31 2019

In attendance about 15 individuals, some of which are mentioned below.

- introduction to node.js tooling group
  - what have we done so far
  - rimraf: challenges in C++
    - the problems with `rm -rf` across filesystems
- Ahmad Nassri:
  - tooling is really huge
  - precompiled CLI envs
  - flags to enable/disable features
  - small distributable
- Dan Ehrenberg:
  - Guy Bedford and I want more feedback from tooling authors in TC39
- Chatter about "small core"
  - Sam Roberts: ‘small core’ vs ‘necessity’
  - Ben Coe: example of crypto. why should it be in core?
- Guy Bedford: bundled cli why?
- Ahmad Nassri: CI env and pipelines for non-node projects that are using node for tooling
  - needing to install a runtime is pain for users
  - zeit made “pkg” which helps solve distributing apps, hacks entry point into node
  - `ncc` mentioned
- Sam Roberts & Joyee Chung: we can do work to enable custom entry points
- Blaine Bublitz: I don’t want to maintain v8-flags anymore.
  - `process.allowedNodeEnvironmentFlags` mentioned
  - V8/@hashseed has not been eager to expose accepted flags via an API, because he feels it implies support
- Jeremiah Senkpiel says something about `NODE_OPTIONS`...
- started to discuss why argument parsing should be in core
  - not sure who said this but:
    - Rust has a good getopt thing where you iterate over stuff and can customize it
    - Chris Hiller explains that if argument parsing is to be added, it makes sense to use the consensus on functionality which was organically determined by userland arg parsing modules (in so many words)

Sam Roberts adds in a post-meeting summary:

> Issue that we talked about a bunch is the issue of not being able to bundle
> CLI's as a single binary... Its a strength of go, and a weakness of node/npm.
> It really hits npm,inc, because a lot of their users aren't node users, but are
> using "javascript" cli tooling, which means node tooling, so they need a
> working node/npm install. This can cause issues, as Gireesh has seen,
> particularly for people who don't even want to use node installing it can be a
> pain.
