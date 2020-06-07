# Code Review Guidelines For Typescript Projects

## Introduction

Something here.

- [Introduction](#introduction)
- [The Guidelines](#the-guidelines)
  - [How To Provide Feedback](#how-to-provide-feedback)
  - [Before You Review The Code](#before-you-review-the-code)
  - [Review Against The Coding Standards](#review-against-the-coding-standards)
  - [Approval Criteria](#approval-criteria)

## The Guidelines

### How To Provide Feedback

1. All feedback must be polite and professional at all times.
2. Split the feedback into two clear sections: GENERAL and SPECIFIC.
3. GENERAL FEEDBACK is all the feedback that isn't about specific lines of code.
4. SPECIFIC FEEDBACK is about the details of the proposal or implementation.
5. Don't be an ass about it.

### Before You Review The Code

1. Is there an open issue for the pull request?
2. Does it fit within the existing scope of the library?
3. Does it fit our goals for the library?

### Review Against The Coding Standards

**Everything in our [coding standards][coding standards] is mandatory.**

We all have limited time to spend on doing code reviews. Our _criteria levels_ are there to help you make the most use of the time you have available.

1. All pull requests must be reviewed against the latest tagged version of our [coding standards][coding standards].
2. Check against _all_ Key criteria for all contributors, including maintainers.
3. Check against Major criteria for all contributors.
4. Check against Minor criteria for all new, or infrequent contributors.
5. Your feedback must *clearly explain* which specific coding standards have not been met, and why.

### Approval Criteria

1. Does the pull request apply cleanly against the latest `develop` branch?
2. Do all of the unit tests pass?

[coding standards]: https://github.com/SafelyTyped/ts-coding-standards/blob/master/STANDARDS.md