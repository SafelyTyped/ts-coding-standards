# Structural Typing

Most programming languages use either [nominal typing][Nominal Typing] or _structural typing_.

For example:

```typescript
interface Cat {
    legs: number;
}

interface Dog {
    legs: number;
}
```

* In _nominal typing_, `Cat` and `Dog` are different types, because their names are different.
* In _structural typing_, `Cat` and `Dog` are the same type, because their structure is the same.

_Structural typing_ is closer to the original concept of object-oriented programming. It allows us to work with data based on its behaviours, rather than its name.


At first glance, _structural typing_ is less [robust][ROBUSTNESS] than [nominal typing][Nominal Typing]. If you pass in the wrong type of data, but it happens to have the same structure as the correct type of data, the compiler cannot warn you about your mistake.

However, _structural typing_ makes it easier to reuse code - and reusing tested code is an important way to improve the robustness of an app. We don't have to put up with limitations or bugs in existing types that we cannot modify. We can make our own types, and as long as they have the same structure, we can use them wherever the existing type is accepted.

And, you can reduce the risks of passing in the wrong type of data by using [type branding][Branded Type] on classes and interfaces.

Typescript uses _structural typing_, because the underlying Javascript engines use _structural typing_.

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
