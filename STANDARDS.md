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
Key   | These are the items that define our purpose.
Major | Getting these right first time avoids significant bugs, expensive rework, and backwards-compatibility breaks.
Minor | These are consistency / stylistic / philosophical points.

## Categories

To make it easier to find things, we've broken up the coding standards into these groups:

Category           | ID  | Description
-------------------|-----|------
Documentation      | .1. |
Errors             | .2. |
Functions          | .8. |
Naming Conventions | .3. |
Package Management | .4. |
Types              | .6. |
Type Guards        | .7. |
Unit Tests         | .5. |

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

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Key | [1.2.1][1.2.1] | Errors | Every function that has error conditions must accept an `OnError` handler. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Key | [1.5.1][1.5.1] | Unit Tests | All code must have 100% code coverage. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS], [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Robustness][ROBUSTNESS]
Key | [1.6.1][1.6.1] | Types | All instantiable types must have a smart constructor. | [Robustness][ROBUSTNESS]
Key | [1.6.2][1.6.2] | Types | Every instantiable type must have a type guard. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]

## Major Criteria

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Major | [2.3.1][2.3.1] | Naming Conventions | All functions and methods that return a function must be called `buildXXX()`. | [Adoption][ADOPTION]
Major | [2.3.2][2.3.2] | Naming Conventions | All smart constructors must be prefixed with `makeXXX()`. | [Adoption][ADOPTION]
Major | [2.3.3][2.3.3] | Naming Conventions | All type guards must be prefixed with `isXXX()`. | [Adoption][ADOPTION]
Major | [2.3.4][2.3.4] | Naming Conventions | All type guarantees must be prefixed with `mustBeXXX()`. | [Adoption][ADOPTION]
Major | [2.5.1][2.5.1] | Unit Tests | Use mocks as a last resort. | [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Robustness][ROBUSTNESS]
Major | [2.6.1][2.6.1] | Types | All base classes must have a `protected` constructor. | [Robustness][ROBUSTNESS], [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.6.2][2.6.2] | Types | All generic types must provide an `AnyXXX` type. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Major | [2.7.1][2.7.1] | Type Guards | Type guards must not accept the `any` type. Use `unknown` instead. | [Robustness][ROBUSTNESS]
Major | [2.8.1][2.8.1] | Functions | All function signatures must follow the same pattern. | [Adoption][ADOPTION], [Correctness][CORRECTNESS], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]
Major | [2.8.2][2.8.2] | Functions | Functions should use dependency injection. | [Adoption][ADOPTION], [Testability][TESTABILITY]
Major | [2.8.3][2.8.3] | Functions | Every mandatory dependency must be a named function parameter. | [Correctness][CORRECTNESS]
Major | [2.8.4][2.8.4] | Functions | Every user-supplied input must be a named parameter. | [Adoption][ADOPTION], [Correctness][CORRECTNESS]
Major | [2.8.5][2.8.5] | Functions | Avoid optional user-supplied inputs. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE], [Testability][TESTABILITY]
Major | [2.8.6][2.8.6] | Functions | User-supplied options must be a single options parameter. | [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.8.7][2.8.7] | Functions | Every property of the _user-supplied options_ parameter must be optional. | [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.8.8][2.8.8] | Functions | Ever user-supplied option must have a default value. | [Adoption][ADOPTION], [Testability][TESTABILITY]
Major | [2.8.9][2.8.9] | Functions | Functional options must be captured as a rest parameter. | [Adoption][ADOPTION]

## Minor Criteria

Priority | ID | Category | Criteria | Impacts
---------|-------|---------------|---------------------------------|--------
Minor    | [3.1.1][3.1.1] | Documentation | Every exported item must have a docblock. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.1.2][3.1.2] | Documentation | Docblocks must begin with the name of the item they document. | [Adoption][ADOPTION]
Minor | [3.1.3][3.1.3] | Documentation | Docblocks must use whole sentences. | [Adoption][ADOPTION]
Minor | [3.1.4][3.1.4] | Documentation | Docblocks must use Typedoc tags. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.1.5][3.1.5] | Documentation | Write docblocks for overridden methods. | [Adoption][ADOPTION]
Minor | [3.1.6][3.1.6] | Documentation | Write docblocks for methods inherited from interfaces. | [Adoption][ADOPTION]
Minor | [3.3.1][3.3.1] | Naming Conventions | Every function or method must start with `<verb><noun>`. | [Adoption][ADOPTION]
Minor | [3.3.2][3.3.2] | Naming Conventions | Use camelCase for all function names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.3][3.3.3] | Naming Conventions | Use camelCase for all variable names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.4][3.3.4] | Naming Conventions | Use SCREAMING_SNAKE_CASE for all constants. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.5][3.3.5] | Naming Conventions | Use PascalCase for all interface names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.6][3.3.6] | Naming Conventions | Use camelCase for all interface property names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.7][3.3.7] | Naming Conventions | Use PascalCase for all class names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.8][3.3.8] | Naming Conventions | Use camelCase for all class property names. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.9][3.3.9] | Naming Conventions | Prefix private and protected class attributes with an underscore. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.10][3.3.10] | Naming Conventions | All Error class names must end with `Error`. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.3.11][3.3.11] | Naming Conventions | All user-supplied option classes/interface names must end with `Options`. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS]
Minor | [3.6.1][3.6.1] | Types | Every interface that is meant to be implemented must define an `implementsXXX()` method. | [Robustness][ROBUSTNESS]
Minor | [3.7.1][3.7.1] | Type Guards | Every type guard must have a unit test that proves it is a _type predicate_. | [Robustness][ROBUSTNESS]
Minor | [3.8.1][3.8.1] | Functions | Create a type for your function's user-supplied options. | [Adoption][ADOPTION]
Minor | [3.8.2][3.8.2] | Functions | Limit user-supplied options to optional dependencies. | [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Testability][TESTABILITY]

[ADOPTION]: ./impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ./impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ./impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ./impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: impacted-areas/ROBUSTNESS.md
[SECURITY]: impacted-areas/SECURITY.md
[TESTABILITY]: impacted-areas/TESTABILITY.md
[1.2.1]: ./categories/errors/1.2.1.md
[1.5.1]: ./categories/unit-tests/1.5.1.md
[1.6.1]: ./categories/types/1.6.1.md
[1.6.2]: ./categories/types/1.6.2.md
[2.3.1]: ./categories/naming-conventions/2.3.1.md
[2.3.2]: ./categories/naming-conventions/2.3.2.md
[2.3.3]: ./categories/naming-conventions/2.3.3.md
[2.3.4]: ./categories/naming-conventions/2.3.4.md
[2.5.1]: ./categories/unit-tests/2.5.1.md
[2.6.1]: ./categories/types/2.6.1.md
[2.6.2]: ./categories/types/2.6.2.md
[2.7.1]: ./categories/type-guards/2.7.1.md
[2.8.1]: ./categories/functions/2.8.1.md
[2.8.2]: ./categories/functions/2.8.2.md
[2.8.3]: ./categories/functions/2.8.3.md
[2.8.4]: ./categories/functions/2.8.4.md
[2.8.5]: ./categories/functions/2.8.5.md
[2.8.6]: ./categories/functions/2.8.6.md
[2.8.7]: ./categories/functions/2.8.7.md
[2.8.8]: ./categories/functions/2.8.8.md
[2.8.9]: ./categories/functions/2.8.9.md
[2.8.10]: ./categories/functions/2.8.10.md
[3.1.1]: ./categories/documentation/3.1.1.md
[3.1.2]: ./categories/documentation/3.1.2.md
[3.1.3]: ./categories/documentation/3.1.3.md
[3.1.4]: ./categories/documentation/3.1.4.md
[3.1.5]: ./categories/documentation/3.1.5.md
[3.1.6]: ./categories/documentation/3.1.6.md
[3.3.1]: ./categories/naming-conventions/3.3.1.md
[3.3.2]: ./categories/naming-conventions/3.3.2.md
[3.3.3]: ./categories/naming-conventions/3.3.3.md
[3.3.4]: ./categories/naming-conventions/3.3.4.md
[3.3.5]: ./categories/naming-conventions/3.3.5.md
[3.3.6]: ./categories/naming-conventions/3.3.6.md
[3.3.7]: ./categories/naming-conventions/3.3.7.md
[3.3.8]: ./categories/naming-conventions/3.3.8.md
[3.3.9]: ./categories/naming-conventions/3.3.9.md
[3.3.10]: ./categories/naming-conventions/3.3.10.md
[3.3.11]: ./categories/naming-conventions/3.3.11.md
[3.6.1]: ./categories/types/3.6.1.md
[3.7.1]: ./categories/type-guards/3.7.1.md
[3.8.1]: ./categories/functions/3.8.1.md
[3.8.2]: ./categories/functions/3.8.2.md