# Coding Standards

This page is our at-a-glance master list of all of our coding standards.

## ID Scheme

This is guided by the idea that good conversations are impossible if it isn't clear which standard(s) are being discussed.

* Every coding standard as a unique ID.
* Once assigned, this ID will not change.
* If the meaning of the coding standard changes over time, it will be given a new ID.
* Our IDs numeric, and use the `x.y.z` structure:
  - `x` is the impact level
    - `1.` for _key_
    - `2.` for _major_
    - `3.` for _minor_
  - `y` is the category
    - numbers are assigned in the order that we invent the categories
  - `z` is the next available number in that category

## Impact Levels

This is guided by the idea that, "if everything is top priority, then nothing is top priority."

We've split the coding standards up into three different levels of importance.

Level | Description
------|-------------------------------------
Key   | Getting these right first time avoids backwards-compatibility breaks, and other issues that cost our end-users significant time.
Major | Getting these right first time avoids significant bugs or expensive rework.
Minor | These are consistency / stylistic / philosophical points.

## Categories

To make it easier to find things, we've broken up the coding standards into these groups:

Category           | Description
-------------------|------------
Documentation      |
Errors             |
Naming Conventions |
Package Management |
Unit Tests         |

## Impacted Areas

Coding standards must not exist for the sake of it. Each critera must address an issue in one (or more) of these areas:

Area                | Impact
--------------------|-------
[Adoption][ADOPTION]                       | These issues make it harder for people to use our projects in their own work.
[Contributions][CONTRIBUTIONS]             | These issues make it harder for people to contribute to our projects.
[Correctness][CORRECTNESS]                 | These issues make it harder to write code that works as intended.
[Governance][GOVERNANCE]                   | These issues make it harder to run the project.
[Project Maintenance][PROJECT-MAINTENANCE] | These issues make it harder to keep code up-to-date.
[Robustness][ROBUSTNESS]                   | These issues make it harder to write code that copes with the unexpected or unintended.
[Security][SECURITY]                       | These issues lead to breaches in data or unauthorised actions.
[Testability][TESTABILITY]                 | These issues make it harder to provide meaningful tests.

## Key Criteria

Priority | ID | Category | Criteria | Impacts | Description
---------|----|----------|----------|---------|------------

## Major Criteria

Priority | ID | Category | Criteria | Impacts | Description
---------|----|----------|----------|---------|------------

## Minor Criteria

Priority | ID | Category | Criteria | Impacts | Description
---------|----|----------|----------|---------|------------

[ADOPTION]: ./impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ./impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ./impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ./impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: impacted-areas/ROBUSTNESS.md
[SECURITY]: impacted-areas/SECURITY.md
[TESTABILITY]: impacted-areas/TESTABILITY.md