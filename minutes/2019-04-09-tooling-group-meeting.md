# Node.js Foundation Tooling Group Meeting 2019-04-09

## Links

- **Recording**: [https://www.youtube.com/watch?v=uQYvN9OKOrI](https://www.youtube.com/watch?v=uQYvN9OKOrI)

- **GitHub Issue**: [https://github.com/nodejs/tooling/issues/26](https://github.com/nodejs/tooling/issues/26)

- **Minutes Google Doc**: [https://docs.google.com/document/d/1yWrZBXccMq7D9PXQxL8MXOmKBzo355WEFRb1DQmfD78](https://docs.google.com/document/d/1yWrZBXccMq7D9PXQxL8MXOmKBzo355WEFRb1DQmfD78)

## Present

- [Ian Sutherland](https://github.com/iansu)
- [Rebecca Turner](https://github.com/iarna)
- [Christopher Hiller](https://github.com/boneskull)
- [Refael Ackermann](https://github.com/refack)
- [Ben Coe](https://github.com/bcoe)

## Agenda

- shutil module ([#23](https://github.com/nodejs/tooling/issues/23))
  - Reference: [https://docs.python.org/2/library/shutil.html](https://docs.python.org/2/library/shutil.html)
  - Ian is working on it; will implement `rmtree`
  - Refael got some positive feedback on the idea
  - **Action item**: Ian says will have a PR soonish
- argument parsing ([#19](https://github.com/nodejs/tooling/issues/19))
  - See [comparison matrix](https://github.com/nodejs/tooling/issues/19#issuecomment-479604245)
  - There's agreement in userland on what an argument parser should do (at minimum)
  - Importantly, there are no _conflicts_
  - We should move forward with a PR with these minimal features
    - We should prioritize out-of-box usage (the "simple" use case) over something libs can be built on (for now)
    - But should not completely disregard this
    - **Action item:** Create a place to discuss & create proof-of-concepts (Chris); invite attendees
- Ben: why are we using `cross-spawn` / `execa`?
  - He notes ~10 Windows-related problems, many seem like bugs
  - Refael: e.g., `exec` is too low-level, too opinionated; maybe a new API instead of fixing the old one, since it will surprise/break people
  - Rebecca: lets put it in `shutil`
  - No action item for now
- Ben: `uuid` in a std module space in the browser
  - He's been talking w/ [Dan Ehrenberg](https://github.com/littledan); experimenting with how adding/implementing a standard module works in TC39
  - Will talk more next meeting
