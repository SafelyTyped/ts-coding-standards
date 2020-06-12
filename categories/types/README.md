# Types Coding Standards

Table of Contents:
- [Introduction](#introduction)
- [What Is In-Scope?](#what-is-in-scope)
- [What Is Out Of Scope?](#what-is-out-of-scope)
- [Coding Standards](#coding-standards)

## Introduction

We need to make it as easy as possible for [end-users][End-User] to be able to use our types as building blocks.

_Types_ are the atomic building blocks of our initiative to improve software quality. There's no point in putting all this effort into software if people can't reuse it.

## What Is In-Scope?

Currently in-scope are the behaviour and properties of:

* all base classes
* all classes that can be instantiated
* all interfaces that describe [data bags][Data Bag]
* all [branded][Branded Type] or [flavoured][Flavoured Type] types

## What Is Out Of Scope?

Currently out-of-scope includes:

* functions, including their [function signature][Function Signature]. See the [Functions][functions] category for those.
* interfaces that implement [protocols][Protocol]. See the [Protocols & Extensions][protocols-extensions] category for these.
* implementation details of classes and functions. See the [Coding Conventions][coding-conventions] category for those.

## Coding Standards

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Key | [1.6.1][1.6.1] | Types | All instantiable types must have a smart constructor. | [Robustness][ROBUSTNESS]
Key | [1.6.2][1.6.2] | Types | Every instantiable type must have a type guard. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]
Key | [1.6.3][1.6.3] | Types | Every instantiable type must have a type guarantee. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]
Major | [2.6.1][2.6.1] | Types | All base classes must have a `protected` constructor. | [Robustness][ROBUSTNESS], [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.6.2][2.6.2] | Types | All generic types must provide an `AnyXXX` type. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Major | [2.6.3][2.6.3] | Types | All public class constructors must be smart constructors. | [Adoption][ADOPTION], [Robustness][ROBUSTNESS]
Minor | [3.6.1][3.6.1] | Types | Every interface that is meant to be implemented must define an `implementsXXX()` method. | [Robustness][ROBUSTNESS]
Minor | [3.6.2][3.6.2] | Types | Do not create static factory methods. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]

[ADOPTION]: ../../impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ../../impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ../../impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ../../impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: ../../impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: ../../impacted-areas/ROBUSTNESS.md
[SECURITY]: ../../impacted-areas/SECURITY.md
[TESTABILITY]: ../../impacted-areas/TESTABILITY.md
[coding-conventions]: ../coding-conventions/README.md
[documentation]: ../documentation/README.md
[errors]: ../errors/README.md
[functions]: ../functions/README.md
[naming-conventions]: ../naming-conventions/README.md
[package-management]: ../package-management/README.md
[protocols-extensions]: ../protocols-extensions/README.md
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
[1.6.1]: ./1.6.1.md
[1.6.2]: ./1.6.2.md
[1.6.3]: ./1.6.3.md
[2.6.1]: ./2.6.1.md
[2.6.2]: ./2.6.2.md
[2.6.3]: ./2.6.3.md
[3.6.1]: ./3.6.1.md
[3.6.2]: ./3.6.2.md