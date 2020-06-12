# CATEGORY TEMPLATE

Table of Contents:
- [Introduction](#introduction)
- [What Is In Scope?](#what-is-in-scope)
- [What Is Out Of Scope?](#what-is-out-of-scope)
- [Coding Standards](#coding-standards)

## Introduction

Have you ever come back to a piece of code you wrote months ago, and found you'd forgotten what it did or how it worked? Ever given up trying to use a third-party library because you couldn't figure out how to use it, or you just couldn't get a vital part of it to work for you?

These are the problems that documentation aims to prevent.

We do not believe that code can be adequate documentation on its own. At best, code explains the "how" - assuming you can follow it. Code alone cannot explain the "what" and the "why".

We do not believe in relying on the accumulated knowledge in individual contributors either:

* Code - both good and bad - normally outlives the involvement of individual contributors.
* Our project is remote and distributed all around the world. Written communication is a vital part of success remote collaboration.
* Write things down to avoid relying on the fallability of people's memories over time.
* In our experience, too many of these gate keepers become toxic roadblocks that prevent new people from becoming project contributors.

Documentation plays an important role in getting new [end-users][End-User] to start using our code. It also speeds up the process of working with our code day in, and day out.

Unfortunately, good documentation is hard to write. Not everyone can do it. It also takes a lot of time. Not everyone has the time. It's also expensive to maintain over time. It's far too easy to change code and not find all the documentation that needs to change too.

So we've had to make a compromise here.

* Our _minimum standard_ is useable reference documentation.
* Tutorial documentation is a nice-to-have on top, but we don't expect anything beyond a 'Getting Started' guide.

We've picked [Typedoc](https://typedoc.org) as our documentation tool _for now_. We say "for now" because the Typescript documentation tools ecosystem is at an early stage. We're open to moving to a better tool if/when one emerges.

We're following [Microsoft's tsdoc project](https://github.com/microsoft/tsdoc), and when it's stable and well-supported, we'll be changing our standards (and probably our tooling) to adopt it.

## What Is In Scope?

Currently in-scope is:

* anything to do with [docblocks][Docblock]
* anything to do with code comments
* any README files in the root folder of projects

## What Is Out Of Scope?

Currently out-of-scope is:

* anything outside of project git repositories
* these CODING STANDARDS

## Coding Standards

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Minor    | [3.1.1][3.1.1] | Documentation | Every exported item must have a docblock. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.1.2][3.1.2] | Documentation | Docblocks must begin with the name of the item they document. | [Adoption][ADOPTION]
Minor | [3.1.3][3.1.3] | Documentation | Docblocks must use whole sentences. | [Adoption][ADOPTION]
Minor | [3.1.4][3.1.4] | Documentation | Docblocks must use Typedoc tags. | [Adoption][ADOPTION], [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.1.5][3.1.5] | Documentation | Write docblocks for overridden methods. | [Adoption][ADOPTION]
Minor | [3.1.6][3.1.6] | Documentation | Write docblocks for methods inherited from interfaces. | [Adoption][ADOPTION]

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
[3.1.1]: ./3.1.1.md
[3.1.2]: ./3.1.2.md
[3.1.3]: ./3.1.3.md
[3.1.4]: ./3.1.4.md
[3.1.5]: ./3.1.5.md
[3.1.6]: ./3.1.6.md