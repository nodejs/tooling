# Node.js Foundation Tooling Group Meeting 2019-02-05

## Links

- **Recording**: [YouTube](https://youtu.be/fhFOrO-IEdc)
- **GitHub Issue**: [#16](https://github.com/nodejs/tooling/issues/16)
- **Minutes Google Doc**: [Google Doc](https://docs.google.com/document/d/1YQ9Z4Tr_sXUS4YbjtlIsUOJTKoRnKPaCEp29W9rX29w/edit)

## Present

- Tooling team: @nodejs/tooling
- Ben Coe
- Daniel Ehrenberg
- Christopher Hiller
- Ian Sutherland
- Refael Ackermann
- Michel Lopez

## Agenda

- Daniel Ehrenberg from TC39 wants feedback from the broader community
- Daniel would give us some details on stuff we’re interested in
- Ben Coe is interested in transpilers, source maps
  - Daniel:
    - no solid spec for source maps
    - there’s a summary available from TC39 meetings
- Daniel: are there features that would be problematic for transpilers, linting, tree-shaking? Or beneficial
- Refael: how can we simplify bundling? Standardized AST or intermediate representation? E.g., V8 team doesn’t want to expose its AST b/c they don’t want to worry about breaking people, so that’s not where we can get such a thing--would need to come out of standards.  
  - Daniel:
    - Emerging set of standards that wants to reduce the need for bundling
    - “Webpackage”, “bundled exchange” is being prototyped in Chrome
    - A number of difft resources bundled into a single file, sent over the network
    - The hope is that HTTP/2 push would make it cheap to send many items, but browser support and configuration was bad
    - With bundled exchange it woulde include html, css, js, images, video, in a single file
  - Refael on bundling:
    - In tooling world, we have different concerns
    - Bundling tools themselves may or may not be helpful
    - Npm is 27000 files itself when installed
  - Ben: webpack and bundlers create confusion for people
    - Moving towards a standard would reduce confusion in the community
  - Refael: why can’t I webpack my backend? It’s not applicable, but it’s confusing
    - Would ask TC39 to think about JS outside of the browser
  - Daniel:
    - Bundling is not TC39 work, it’s W3C stuff
    - “Import maps” would be necessary (?) for this to work. Web incubator community group, not at TC39 either
  - Ben: at a meta level there’s a disconnect between how a web browser and node represents files
    - Finding more common ground
    - How can we make URIs more palatable to the backend, for example
    - Nobody wants to provide a URI, they just want to require lodash
  - Daniel:
    - Import maps can solve this problem maybe
  - Chris: import maps? Not TC39?
  - Daniel: sometimes its unclear where standards should be developed  
Ben: what’s the best way to have dialog with TC39?
  Daniel: still trying to figure it out. Proposals are developed in open on GitHub, but this doesn’t always work because the people on the proposals don’t have the full context of the people giving feedback
    - Daniel wants to talk to them separately and bring feedback back to TC39
    - But may not be the best idea to have an intermediary
  - Ben: core node collabs have a node-centric view, there’s userland people using node, there’s browserland and browser vendors… nobody sees eye-to-eye necessarily
    - How can the group bridge the gaps?
  - Daniel: we want people prototyping stuff using emerging standards
  - Ben: like babel. We can reach out to tooling authors
  - Chris: does TC39 know about esm? (userland module)
    - Daniel: Yes
  - Daniel: experimentation like using webpackage would be helpful
  - Ben: c8 uses v8 coverage, which is experimentation
    - In the module discussion, it’s frustrating
    - We want to move forward our ecosystem
    - Package maps. But can’t move forward without experimental tooling
  - Daniel: Give feedback to proposals within github issues
  - Chris: a suggestion box!
  - Daniel: We thinking about setting up discourse
    - It can be hard to extract the feedback from angry people
  - Ben:
    - The impact of a tool can be more valuable than a discussion
    - More tools, less conversation!
  - Daniel:
    - There’s an import maps polyfill somewhere
    - Guy Bedford (not present) owns this
Refael: Give us an idea of where TC39 sees itself in the ecosystem
  - Daniel:
    - TC39 sees itself as responsible for the language
    - But it’s unclear where some things land? Are they in the language?
    - Please participate in node open standards repo?
    - Have a call thereafter
  - Ben:  Maybe regular TC39 rep, but not entire meeting
  - Daniel: Will try to show at next meeting to keep conversation going
  
- Chris: meeting how often? 3wks ok?
  - Ben: let’s slack more
  - Chris: maybe go to blessed slack
  - Rick: yes
- Rimraf: Sam Roberts (IBM) will comment on rimraf-in-C++ issue
- Ben: Node is now using my coverage thing
  - Sourcemaps are a big problem
  - Daniel: There’s lack of a proper standard. That’s a problem
    - Edge cases differ in certain places

## Announcements

\*Extracted from **tooling-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

## Q&A, Other

## Upcoming Meetings

- **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.
