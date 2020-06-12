# Coding Standards

This repo holds the coding standards for any Typescript project managed by the SafelyTyped community.

Feel free to adopt them for your own community too :)

## Introduction

The _Safe Types movement_ is, at heart, an initiative to improve software quality. We've chosen to do that by moving [defensive programming][Defensive Programming] from literally everywhere (or nowhere, for projects that don't do any defensive programming) into [type constructors][Smart Constructor].

That simple statement hides a lot of complexity. There's a lot that goes into making a _safe type_:

* [easy to use][ADOPTION] by [end-users][End-User]
* [easy to contribute to][CONTRIBUTIONS]
* [easy to vet][TESTABILITY]
* [work accurately][CORRECTNESS]
* [work reliably][ROBUSTNESS]
* [be secure][SECURITY]

as well as helping us [maintain the code][PROJECT-MAINTENANCE] and [run the project][GOVERNANCE] for the long-term.

### Why Do We Need Coding Standards At All?

_Written coding standards_ are designed to _ensure an acceptable level of consistent software quality_ across our projects.

That's doing a lot of heavy lifting. Let's break it down.

* The whole point of the _SafelyTyped_ projects is to give you tools to raise the quality of your software.
* To achieve that, we believe it's important that all of our code is written, tested and documented to (at least!) the same standard.
* We don't believe that it's possible to achieve consistency unless that standard itself has been documented in a way that's easy to understand.

Even in an office environment - where people can quickly and easily discuss things face-to-face - they are helpful. On a distributed project - where discussions don't happen in real-time, and where contributors can be infrequent - they are essential.

### Where Do These Standards Come From?

They're based on the approach that Stuart has developed and refined over the last 25 years of working on software quality and assurance.

Watch this video to see Stuart talking about this approach:

[![Thumbnail of the Coding Standards Video Title Screen](assets/YouTube-Coding-Standards.png)](https://www.youtube.com/watch?v=bPTUmKc_F_g)

## The Standards

See [STANDARDS.md](STANDARDS.md) for the all-in-one-document list.

## Glossary

We've put together a comprehensive [GLOSSARY.md](./glossary/README.md) to explain all of the jargon that we commonly use in the Safely Typed projects.

[ADOPTION]: ./impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ./impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ./impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ./impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: impacted-areas/ROBUSTNESS.md
[SECURITY]: impacted-areas/SECURITY.md
[TESTABILITY]: impacted-areas/TESTABILITY.md
[Base Class]: glossary/base-class.md
[Branded Type]: glossary/branded-type.md
[Caller]: glossary/caller.md
[CQRS]: glossary/CQRS.md
[Data Bag]: glossary/data-bag.md
[Data Guarantee]: glossary/data-guarantee.md
[Data Guard]: glossary/data-guard.md
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