# Naming Conventions Coding Standards

Table of Contents:
- [Introduction](#introduction)
- [What Is In Scope?](#what-is-in-scope)
- [What Is Out Of Scope?](#what-is-out-of-scope)
- [Coding Standards](#coding-standards)

## Introduction

The language we use matters. And that starts with what we do - and do not - call things.

If we use language consistently, it helps [end-users][End-User] discover our code and our feature more easily. It reduces surprises, and helps to reliminate mistakes. We believe that these are important.

Our choice of language helps to define our sense of community. Our choices say something about what we've come together to achieve. The names we use - and the ones we don't - help all of us contribute.

Some language has no place in the modern workplace. And make no mistake, these projects are to be treated as a modern workplace.

Finally, any industry veteran will tell you that arguments over the names we use are right up there with those over code formatting and the like. It's one of those things that people argue over because they can. Life's too short for that.

## What Is In Scope?

Currently in-scope is:

* the names of classes
* the names of constants
* the names of files
* the names of functions
* the names of interfaces
* the names of methods
* the names of modules
* the names of packages
* the names of types
* the names of variables
* the names of versions

and any other artefacts we've not covered in the list above.

## What Is Out Of Scope?

Nothing. If it's a name, then that name is in-scope.

## Coding Standards

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Key | [1.3.1][1.3.1] | Naming Conventions | All names must be racially-neutral. | [Adoption][ADOPTION]
Major | [2.3.1][2.3.1] | Naming Conventions | All functions and methods that return a function must be called `buildXXX()`. | [Adoption][ADOPTION]
Major | [2.3.2][2.3.2] | Naming Conventions | All smart constructors must be prefixed with `makeXXX()`. | [Adoption][ADOPTION]
Major | [2.3.3][2.3.3] | Naming Conventions | All type guards must be prefixed with `isXXX()`. | [Adoption][ADOPTION]
Major | [2.3.4][2.3.4] | Naming Conventions | All type guarantees must be prefixed with `mustBeXXX()`. | [Adoption][ADOPTION]
Minor | [3.3.1] | Naming Conventions | Every function or method must start with `<verb><noun>`. | [Adoption][ADOPTION]
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
Key | [3.3.12][3.3.12] | Naming Conventions | Do not name anything `blacklist` or `whitelist`. | [Adoption][ADOPTION]

[ADOPTION]: ../../impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ../../impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ../../impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ../../impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: ../../impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: ../../impacted-areas/ROBUSTNESS.md
[SECURITY]: ../../impacted-areas/SECURITY.md
[TESTABILITY]: ../../impacted-areas/TESTABILITY.md
[coding-conventions]: ../coding-conventions/README.md
[data-guarantees]: ../data-guarantees/README.md
[data-guards]: ../data-guards/README.md
[documentation]: ../documentation/README.md
[errors]: ../errors/README.md
[functions]: ../functions/README.md
[naming-conventions]: ../naming-conventions/README.md
[package-management]: ../package-management/README.md
[protocols-extensions]: ../protocols-extensions/README.md
[smart-constructors]: ../smart-constructors/README.md
[type-guarantees]: ../type-guarantees/README.md
[type-guards]: ../type-guards/README.md
[types]: ../types/README.md
[unit-tests]: ../unit-tests/README.md
[Base Class]: ../../glossary/base-class.md
[Branded Type]: ../../glossary/branded-type.md
[Caller]: ../../glossary/caller.md
[CQRS]: ../../glossary/CQRS.md
[Data Bag]: ../../glossary/data-bag.md
[Data Guarantee]: ../../glossary/data-guarantee.md
[Data Guard]: ../../glossary/data-guard.md
[Default Value]: ../../glossary/default-value.md
[Defensive Programming]: ../../glossary/defensive-programming.md
[Dependency]: ../../glossary/dependency.md
[Dependency Injection]: ../../glossary/dependency-injection.md
[Docblock]: ../../glossary/docblock.md
[End-User]: ../../glossary/end-user.md
[Entity]: ../../glossary/entity.md
[Exported Item]: ../../glossary/exported-item.md
[Extension]: ../../glossary/extension.md
[Flavoured Type]: ../../glossary/flavoured-type.md
[Function Prefix]: ../../glossary/function-prefix.md
[Function Signature]: ../../glossary/function-signature.md
[Hard-Coded]: ../../glossary/hard-coded.md
[Identity]: ../../glossary/identity.md
[Identity Function]: ../../glossary/identity-function.md
[Identity Type]: ../../glossary/identity-type.md
[Immutability]: ../../glossary/immutability.md
[Inherited Method]: ../../glossary/inherited-method.md
[Instantiable Type]: ../../glossary/instantiable-type.md
[Mandatory Dependency]: ../../glossary/mandatory-dependency.md
[No-Op]: ../../glossary/no-op.md
[Nominal Typing]: ../../glossary/nominal-typing.md
[Optional Input]: ../../glossary/optional-input.md
[Overridden Method]: ../../glossary/overridden-method.md
[Plain Object]: ../../glossary/plain-object.md
[Primitive Type]: ../../glossary/primitive-type.md
[Protocol]: ../../glossary/protocol.md
[Refined Type]: ../../glossary/refined-type.md
[Rest Parameter]: ../../glossary/rest-parameter.md
[Reusability]: ../../glossary/reusability.md
[Side Effects]: ../../glossary/side-effects.md
[Smart Constructor]: ../../glossary/smart-constructor.md
[Structural Typing]: ../../glossary/structural-typing.md
[Type Alias]: ../../glossary/type-alias.md
[Type Casting]: ../../glossary/type-casting.md
[Type Guarantee]: ../../glossary/type-guarantee.md
[Type Guard]: ../../glossary/type-guard.md
[Type Inference]: ../../glossary/type-inference.md
[Type Predicate]: ../../glossary/type-predicate.md
[User-Supplied Functional Options]: ../../glossary/user-supplied-functional-options.md
[User-Supplied Input]: ../../glossary/user-supplied-input.md
[User-Supplied Options]: ../../glossary/user-supplied-options.md
[User-Supplied Optional Dependencies]: ../../glossary/user-supplied-optional-dependencies.md
[Value]: ../../glossary/value.md
[Value Object]: ../../glossary/value-object.md
[1.3.1]: ./1.3.1.md
[2.3.1]: ./2.3.1.md
[2.3.2]: ./2.3.2.md
[2.3.3]: ./2.3.3.md
[2.3.4]: ./2.3.4.md
[3.3.1]: ./3.3.1.md
[3.3.2]: ./3.3.2.md
[3.3.3]: ./3.3.3.md
[3.3.4]: ./3.3.4.md
[3.3.5]: ./3.3.6.md
[3.3.6]: ./3.3.6.md
[3.3.7]: ./3.3.7.md
[3.3.8]: ./3.3.8.md
[3.3.9]: ./3.3.9.md
[3.3.10]: ./3.3.10.md
[3.3.11]: ./3.3.11.md
[3.3.12]: ./3.3.12.md