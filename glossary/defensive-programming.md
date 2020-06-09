# Defensive Programming

_Defensive programming_ is a programming technique designed to make your code more [robust][ROBUSTNESS].

* Inputs are treated as untrusted data. They are validated before they are used.
* Outputs are treated as incorrect data. They are validated before they are returned to the [caller][Caller].

Traditionally, this was done inside every single function in a library or application:

* Every input was validated.
* Every output was validated.

The idea was to prevent unexpected / unsafe data from reaching the function's logic, and to prevent "bad" (as in incorrect values or even the wrong data type) from propagating to other functions (where they could corrupt databases, cause security holes, and crash the app).

In languages with limited and/or unenforced type systems, _defensive programming_ was really the only technique available to create robust code.

Unfortunately, while the concept works, it's really really expensive:

* Someone has to write every single line of input validation code. That eats up a lot of time.
* This has to be done everywhere. If it isn't, you end up with paths through the code that may be unsafe / insecure (known as _planetary alignment_).
* All this code has to be executed by the CPU. That's expensive, especially because the same piece of data would end up being verified and re-verified multiple times.
* Someone has to write tests for every single line of input validation code too. Untested validation code is almost as unsafe as having no validation code at all.
* It's currently impossible to perform static analysis on defensive code to prove that everything is safe.

That's why Stuart says, "Zero defect code is perfectly possible; you just can't afford what it costs to create it".

The reality is that many programmers (and projects as a whole) do not add defensive programming to their code. And the ones that do, almost never succeed in adding it to 100% of the code base.

The [Safely Typed movement][Safely Type Website] was born out of research into how to replace defensive programming.

[ADOPTION]: ../impacted-areas/ADOPTION.md
[CONTRIBUTIONS]: ../impacted-areas/CONTRIBUTIONS.md
[CORRECTNESS]: ../impacted-areas/CORRECTNESS.md
[GOVERNANCE]: ../impacted-areas/GOVERNANCE.md
[PROJECT-MAINTENANCE]: ../impacted-areas/PROJECT-MAINTENANCE.md
[ROBUSTNESS]: ../impacted-areas/ROBUSTNESS.md
[SECURITY]: ../impacted-areas/SECURITY.md
[TESTABILITY]: ../impacted-areas/TESTABILITY.md
[Base Class]: ./base-class.md
[Branded Type]: ./branded-type.md
[Caller]: ./caller.md
[CQRS]: ./CQRS.md
[Data Bag]: ./data-bag.md
[Data Guard]: ./data-guard.md
[Data Guarantee]: ./data-guarantee.md
[Default Value]: ./default-value.md
[Defensive Programming]: ./defensive-programming.md
[Dependency]: ./dependency.md
[Dependency Injection]: ./dependency-injection.md
[Docblock]: ./docblock.md
[End-User]: ./end-user.md
[Entity]: ./entity.md
[Exported Item]: ./exported-item.md
[Flavoured Type]: ./flavoured-type.md
[Function Prefix]: ./function-prefix.md
[Function Signature]: ./function-signature.md
[Hard-Coded]: ./hard-coded.md
[Identity]: ./identity.md
[Immutability]: ./immutability.md
[Inherited Method]: ./inherited-method.md
[Instantiable Type]: ./instantiable-type.md
[Mandatory Dependency]: ./mandatory-dependency.md
[Nominal Typing]: ./nominal-typing.md
[Optional Input]: ./optional-input.md
[Overridden Method]: ./overridden-method.md
[Plain Object]: ./plain-object.md
[Primitive Type]: ./primitive-type.md
[Protocol]: ./protocol.md
[Refined Type]: ./refined-type.md
[Rest Parameter]: ./rest-parameter.md
[Reusability]: ./reusability.md
[Side Effects]: ./side-effects.md
[Smart Constructor]: ./smart-constructor.md
[Structural Typing]: ./structural-typing.md
[Type Alias]: ./type-alias.md
[Type Casting]: ./type-casting.md
[Type Guarantee]: ./type-guarantee.md
[Type Guard]: ./type-guard.md
[Type Inference]: ./type-inference.md
[Type Predicate]: ./type-predicate.md
[Type Signature]: ./type-signature.md
[User-Supplied Functional Options]: ./user-supplied-functional-options.md
[User-Supplied Input]: ./user-supplied-input.md
[User-Supplied Options]: ./user-supplied-options.md
[User-Supplied Optional Dependencies]: ./user-supplied-optional-dependencies.md
[Value]: ./value.md
[Value Object]: ./value-object.md
[Safely Typed Website]: ./https://safelytyped.com