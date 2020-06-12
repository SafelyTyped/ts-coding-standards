# Functions Coding Standards

Table of Contents:
- [Introduction](#introduction)
- [What Is In Scope?](#what-is-in-scope)
- [What Is Out Of Scope?](#what-is-out-of-scope)
- [Coding Standards](#coding-standards)

## Introduction

Practically of our executable code lives in _functions_ and _methods_. Without them, our types aren't _safe_, they're just types.

Any changes we make to _functions_ and _methods_ after they have shipped run the risk of breaking backwards-compatibility. It's important that we get them _right first time_ as much as possible.

Not all _functions_ and _methods_ are equal. Some of them do very specific jobs, and they need additional coding standards to cover that. We've added categories for each of these.

## What Is In Scope?

Currently in-scope are:

* all general points about function design and implementation
* all general points about method design and implementation

## What Is Out Of Scope?

Currently out-of-scope are:

* general points about our preferred coding style; these are covered in the [Coding Conventions][coding-conventions] category
* anything about specific types of function (they get their own, individual categories)

## Coding Standards

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Major | [2.8.1][2.8.1] | Functions | All function signatures must follow the same pattern. | [Adoption][ADOPTION], [Correctness][CORRECTNESS], [Robustness][ROBUSTNESS], [Testability][TESTABILITY]
Major | [2.8.2][2.8.2] | Functions | Functions should use dependency injection. | [Adoption][ADOPTION], [Testability][TESTABILITY]
Major | [2.8.3][2.8.3] | Functions | Every mandatory dependency must be a named function parameter. | [Correctness][CORRECTNESS]
Major | [2.8.4][2.8.4] | Functions | Every user-supplied input must be a named parameter. | [Adoption][ADOPTION], [Correctness][CORRECTNESS]
Major | [2.8.5][2.8.5] | Functions | Avoid optional user-supplied inputs. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE], [Testability][TESTABILITY]
Major | [2.8.6][2.8.6] | Functions | User-supplied options must be a single options parameter. | [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.8.7][2.8.7] | Functions | Every property of the _user-supplied options_ parameter must be optional. | [Project Maintenance][PROJECT-MAINTENANCE]
Major | [2.8.8][2.8.8] | Functions | Ever user-supplied option must have a default value. | [Adoption][ADOPTION], [Testability][TESTABILITY]
Major | [2.8.9][2.8.9] | Functions | Functional options must be captured as a rest parameter. | [Adoption][ADOPTION]
Minor | [3.8.1][3.8.1] | Functions | Create a type for your function's user-supplied options. | [Adoption][ADOPTION]
Minor | [3.8.2][3.8.2] | Functions | Limit user-supplied options to optional dependencies. | [Correctness][CORRECTNESS], [Project Maintenance][PROJECT-MAINTENANCE], [Testability][TESTABILITY]

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
[2.8.1]: ./2.8.1.md
[2.8.2]: ./2.8.2.md
[2.8.3]: ./2.8.3.md
[2.8.4]: ./2.8.4.md
[2.8.5]: ./2.8.5.md
[2.8.6]: ./2.8.6.md
[2.8.7]: ./2.8.7.md
[2.8.8]: ./2.8.8.md
[2.8.9]: ./2.8.9.md
[3.8.1]: ./3.8.1.md
[3.8.2]: ./3.8.2.md