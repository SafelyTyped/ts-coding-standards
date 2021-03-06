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

Category                                       | ID   | Description
-----------------------------------------------|------|------------
[Coding Conventions][coding-conventions]       | .9.  | Ensures a consistent coding style over time.
[Data Guarantees][data-guarantees]             | .11. | Ensures [end-users][End-User] can enforce data contracts reliably.
[Data Guards][data-guards]                     | .12. | Ensures [end-users][End-User] and maintainers can build data guarantees reliably.
[Documentation][documentation]                 | .1.  | Helps [end-users][End-User] and the maintainers understand the what, the how, and the why.
[Errors][errors]                               | .2.  | Ensures our code handles failure in a consistent, production-friendly manner.
[Functions][functions]                         | .8.  | Ensures consistent behaviour from our public module API (and our internal API too).
[Naming Conventions][naming-conventions]       | .3.  | Ensures a consistent and tidier public module API (and our internal API too).
[Package Management][package-management]       | .4.  | Ensures a consistent approach to packages over time.
[Protocols & Extensions][protocols-extensions] | .10. | Ensures a consistent approach to extending types.
[Smart Constructors][smart-constructors]       | .14. | Ensures our types really are safe types.
[Types][types]                                 | .6.  | Ensures our types make for great building blocks.
[Type Guarantees][type-guarantees]             | .13. | Ensures [end-users][End-User] and maintainers can enforce type contracts reliably.
[Type Guards][type-guards]                     | .7.  | Ensures [end-users][End-User] have the [type guards][Type Guard] they need when they need them.
[Unit Tests][unit-tests]                       | .5.  | Ensures we ship less bugs and regressions.

Here they are, listed by ID order too:

Category                                       | ID   | Description
-----------------------------------------------|------|------------
[Documentation][documentation]                 | .1.  | Helps [end-users][End-User] and the maintainers understand the what, the how, and the why.
[Errors][errors]                               | .2.  | Ensures our code handles failure in a consistent, production-friendly manner.
[Naming Conventions][naming-conventions]       | .3.  | Ensures a consistent and tidier public module API (and our internal API too).
[Package Management][package-management]       | .4.  | Ensures a consistent approach to packages over time.
[Unit Tests][unit-tests]                       | .5.  | Ensures we ship less bugs and regressions.
[Types][types]                                 | .6.  | Ensures our types make for great building blocks.
[Type Guards][type-guards]                     | .7.  | Ensures [end-users][End-User] have the [type guards][Type Guard] they need when they need them.
[Functions][functions]                         | .8.  | Ensures consistent behaviour from our public module API (and our internal API too).
[Coding Conventions][coding-conventions]       | .9.  | Ensures a consistent coding style over time.
[Protocols & Extensions][protocols-extensions] | .10. | Ensures a consistent approach to extending types.
[Data Guarantees][data-guarantees]             | .11. | Ensures [end-users][End-User] can enforce data contracts reliably.
[Data Guards][data-guards]                     | .12. | Ensures [end-users][End-User] and maintainers can build data guarantees reliably.
[Type Guarantees][type-guarantees]             | .13. | Ensures [end-users][End-User] and maintainers can enforce type contracts reliably.
[Smart Constructors][smart-constructors]       | .14. | Ensures our types really are safe types.

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
Key | [1.2.2][1.2.2] | Errors | Only `throw` `AppError`s.  | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Key | [1.3.1][1.3.1] | Naming Conventions | All names must be racially-neutral. | [Adoption][ADOPTION]
Key | [1.4.1][1.4.1] | [Package Management][package-management] | Do not ship any code that isn't for production use. | [Project Maintenance][PROJECT-MAINTENANCE], [Security][SECURITY]
Key | [1.5.1][1.5.1] | Unit Tests | All code must have 100% code coverage. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS], [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Robustness][ROBUSTNESS]
Key | [1.6.1][1.6.1] | Types | All instantiable types must have a smart constructor. | [Robustness][ROBUSTNESS]
Key | [1.6.2][1.6.2] | Types | Every instantiable type must have a type guard. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]
Key | [1.6.3][1.6.3] | Types | Every instantiable type must have a type guarantee. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]

## Major Criteria

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Major | [2.3.1][2.3.1] | Naming Conventions | All functions and methods that return a function must be called `buildXXX()`. | [Adoption][ADOPTION]
Major | [2.3.2][2.3.2] | Naming Conventions | All smart constructors must be prefixed with `makeXXX()`. | [Adoption][ADOPTION]
Major | [2.3.3][2.3.3] | Naming Conventions | All type guards must be prefixed with `isXXX()`. | [Adoption][ADOPTION]
Major | [2.3.4][2.3.4] | Naming Conventions | All type guarantees must be prefixed with `mustBeXXX()`. | [Adoption][ADOPTION]
Major | [2.4.1][2.4.1] | [Package Management][package-management] | Export the entire public API from the API's top-level index file. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.5.1][2.5.1] | Unit Tests | Use mocks as a last resort. | [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Robustness][ROBUSTNESS]
Major | [2.6.1][2.6.1] | Types | All base classes must have a `protected` constructor. | [Robustness][ROBUSTNESS], [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.6.2][2.6.2] | Types | All generic types must provide an `AnyXXX` type. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Major | [2.6.3][2.6.3] | Types | All public constructors must be smart constructors. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
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
Major | [2.8.10][2.8.10] | [Functions][functions] | Define `DEFAULT_OPTIONS` for every function that cannot meet [2.8.7][2.8.7].
Major | [2.10.1][2.10.1] | [Protocols and Extensions][protocols-extensions] | Every protocol interface must define an `implementsXXX()` method. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]

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
Minor | [3.3.12][3.3.12] | Naming Conventions | Do not name anything `blacklist` or `whitelist`. | [Adoption][ADOPTION]
Minor | [3.3.13][3.3.13] | [Naming Conventions][naming-conventions] | All default options must be called `XXX_DEFAULT_OPTIONS`. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.3.14][3.3.14] | [Naming Conventions][naming-conventions] | All default values must be called `DEFAULT_XXX`. | [Adoption][ADOPTION]
Minor | [3.4.1][3.4.1] | [Package Management][package-management] | Every module folder must have an index file. | [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.2][3.4.2] | [Package Management][package-management] | Index files must only export the public API. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.3][3.4.3] | [Package Management][package-management] | Put each safe type into its own folder. | [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.4][3.4.4] | [Package Management][package-management] | Put exported classes in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.5][3.4.5] | [Package Management][package-management] | Put exported functions in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.6][3.4.6] | [Package Management][package-management] | Put exported types in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.7][3.4.7] | [Package Management][package-management] | Put exported default values in their own file. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.5.1][3.5.1] | [Unit Tests][unit-tests] | Put fixtures into a folder called `_fixtures`. | [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.6.1][3.6.1] | Types | Every interface that is meant to be implemented must define an `implementsXXX()` method. | [Robustness][ROBUSTNESS]
Minor | [3.6.2][3.6.2] | Types | Do not create static factory methods. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.7.1][3.7.1] | Type Guards | Every type guard must have a unit test that proves it is a _type predicate_. | [Robustness][ROBUSTNESS]
Minor | [3.8.1][3.8.1] | Functions | Create a type for your function's user-supplied options. | [Adoption][ADOPTION]
Minor | [3.8.2][3.8.2] | Functions | Limit user-supplied options to optional dependencies. | [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Testability][TESTABILITY]
Minor | [3.8.3][3.8.3] | [Functions][functions] | Use `DEFAULT_DATA_PATH` for all optional data path parameters. | [Adoption][ADOPTION]

[ADOPTION]: ./impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ./impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ./impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ./impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: impacted-areas/ROBUSTNESS.md
[SECURITY]: impacted-areas/SECURITY.md
[TESTABILITY]: impacted-areas/TESTABILITY.md
[coding-conventions]: categories/coding-conventions/README.md
[data-guarantees]: categories/data-guarantees/README.md
[data-guards]: categories/data-guards/README.md
[documentation]: categories/documentation/README.md
[errors]: categories/errors/README.md
[functions]: categories/functions/README.md
[naming-conventions]: categories/naming-conventions/README.md
[package-management]: categories/package-management/README.md
[protocols-extensions]: categories/protocols-extensions/README.md
[smart-constructors]: categories/smart-constructors/README.md
[type-guarantees]: categories/type-guarantees/README.md
[type-guards]: categories/type-guards/README.md
[types]: categories/types/README.md
[unit-tests]: categories/unit-tests/README.md
[Base Class]: glossary/base-class.md
[Branded Type]: glossary/branded-type.md
[Caller]: glossary/caller.md
[CQRS]: glossary/CQRS.md
[Data Bag]: glossary/data-bag.md
[Data Guarantee]: glossary/data-guarantee.md
[Data Guard]: glossary/data-guard.md
[Data Path]: glossary/data-path.md
[Default Value]: glossary/default-value.md
[Defensive Programming]: glossary/defensive-programming.md
[Dependency]: glossary/dependency.md
[Dependency Injection]: glossary/dependency-injection.md
[Docblock]: glossary/docblock.md
[End-User]: glossary/end-user.md
[Entity]: glossary/entity.md
[Exported Item]: glossary/exported-item.md
[Extension]: glossary/extension.md
[Flavoured Type]: glossary/flavoured-type.md
[Function Prefix]: glossary/function-prefix.md
[Function Signature]: glossary/function-signature.md
[Hard-Coded]: glossary/hard-coded.md
[Identity]: glossary/identity.md
[Identity Function]: glossary/identity-function.md
[Identity Type]: glossary/identity-type.md
[Immutability]: glossary/immutability.md
[Inherited Method]: glossary/inherited-method.md
[Instantiable Type]: glossary/instantiable-type.md
[Mandatory Dependency]: glossary/mandatory-dependency.md
[No-Op]: glossary/no-op.md
[Nominal Typing]: glossary/nominal-typing.md
[Optional Input]: glossary/optional-input.md
[Overridden Method]: glossary/overridden-method.md
[Plain Object]: glossary/plain-object.md
[Primitive Type]: glossary/primitive-type.md
[Protocol]: glossary/protocol.md
[Refined Type]: glossary/refined-type.md
[Rest Parameter]: glossary/rest-parameter.md
[Reusability]: glossary/reusability.md
[Side Effects]: glossary/side-effects.md
[Smart Constructor]: glossary/smart-constructor.md
[Structural Typing]: glossary/structural-typing.md
[Type Alias]: glossary/type-alias.md
[Type Casting]: glossary/type-casting.md
[Type Guarantee]: glossary/type-guarantee.md
[Type Guard]: glossary/type-guard.md
[Type Inference]: glossary/type-inference.md
[Type Predicate]: glossary/type-predicate.md
[User-Supplied Functional Options]: glossary/user-supplied-functional-options.md
[User-Supplied Input]: glossary/user-supplied-input.md
[User-Supplied Options]: glossary/user-supplied-options.md
[User-Supplied Optional Dependencies]: glossary/user-supplied-optional-dependencies.md
[Value]: glossary/value.md
[Value Object]: glossary/value-object.md
[1.2.1]: ./categories/errors/1.2.1.md
[1.2.2]: ./categories/errors/1.2.2.md
[1.5.1]: ./categories/unit-tests/1.5.1.md
[1.6.1]: ./categories/types/1.6.1.md
[1.6.2]: ./categories/types/1.6.2.md
[1.6.3]: ./categories/types/1.6.3.md
[1.3.1]: ./categories/naming-conventions/1.3.1.md
[2.3.1]: ./categories/naming-conventions/2.3.1.md
[2.3.2]: ./categories/naming-conventions/2.3.2.md
[2.3.3]: ./categories/naming-conventions/2.3.3.md
[2.3.4]: ./categories/naming-conventions/2.3.4.md
[1.4.1]: ./categories/package-management/1.4.1.md
[2.4.1]: ./categories/package-management/2.4.1.md
[2.5.1]: ./categories/unit-tests/2.5.1.md
[2.6.1]: ./categories/types/2.6.1.md
[2.6.2]: ./categories/types/2.6.2.md
[2.6.3]: ./categories/types/2.6.3.md
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
[2.10.1]: ./categories/protocols-extensions/2.10.1.md
[3.1.1]: ./categories/documentation/3.1.1.md
[3.1.2]: ./categories/documentation/3.1.2.md
[3.1.3]: ./categories/documentation/3.1.3.md
[3.1.4]: ./categories/documentation/3.1.4.md
[3.1.5]: ./categories/documentation/3.1.5.md
[3.1.6]: ./categories/documentation/3.1.6.md
[3.2.1]: ./categories/errors/3.2.1.md
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
[3.3.12]: ./categories/naming-conventions/3.3.12.md
[3.3.13]: ./categories/naming-conventions/3.3.13.md
[3.3.14]: ./categories/naming-conventions/3.3.14.md
[3.4.1]: ./categories/package-management/3.4.1.md
[3.4.2]: ./categories/package-management/3.4.2.md
[3.4.3]: ./categories/package-management/3.4.3.md
[3.4.4]: ./categories/package-management/3.4.4.md
[3.4.5]: ./categories/package-management/3.4.5.md
[3.4.6]: ./categories/package-management/3.4.6.md
[3.4.7]: ./categories/package-management/3.4.7.md
[3.5.1]: ./categories/unit-tests/3.5.1.md
[3.6.1]: ./categories/types/3.6.1.md
[3.6.2]: ./categories/types/3.6.2.md
[3.7.1]: ./categories/type-guards/3.7.1.md
[3.8.1]: ./categories/functions/3.8.1.md
[3.8.2]: ./categories/functions/3.8.2.md
[3.8.3]: ./categories/functions/3.8.3.md