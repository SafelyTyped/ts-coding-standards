# Package Management Coding Standards

Table of Contents:
- [Introduction](#introduction)
- [What Is In Scope?](#what-is-in-scope)
- [What Is Out Of Scope?](#what-is-out-of-scope)
- [Coding Standards](#coding-standards)

## Introduction

Eventually, we have to release our code. It's the only way to get our code into the hands of our [end-users][End-User]. We do this by creating packages.

## What Is In Scope?

Currently in-scope are:

* the structure of our packages
* the versioning of our packages

## What Is Out Of Scope?

Currently out-of-scope are:

* the naming of our packages

## Coding Standards

Priority | ID | Category | Criteria | Impacts
---------|----|----------|----------|--------
Key | [1.4.1][1.4.1] | [Package Management][Package Management] | Do not ship any code that isn't for production use. | [Project Maintenance][PROJECT-MAINTENANCE], [Security][SECURITY]
Major | [2.4.1][2.4.1] | [Package Management][package-management] | Export the entire public API from the API's top-level index file. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.1][3.4.1] | [Package Management][package-management] | Every module folder must have an index file. | [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.2][3.4.2] | [Package Management][package-management] | Index files must only export the public API. | [Adoption][ADOPTION], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.3][3.4.3] | [Package Management][package-management] | Put each safe type into its own folder. | [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.4][3.4.4] | [Package Management][package-management] | Put exported classes in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.5][3.4.5] | [Package Management][package-management] | Put exported functions in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.6][3.4.6] | [Package Management][package-management] | Put exported types in their own files. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]
Minor | [3.4.7][3.4.7] | [Package Management][package-management] | Put exported default values in their own file. | [Contributions][CONTRIBUTIONS], [Project Maintenance][PROJECT-MAINTENANCE]

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
[1.4.1]: ./1.4.1.md
[2.4.1]: ./2.4.1.md
[3.4.1]: ./3.4.1.md
[3.4.2]: ./3.4.2.md
[3.4.3]: ./3.4.3.md
[3.4.4]: ./3.4.4.md
[3.4.5]: ./3.4.5.md