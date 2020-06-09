# No-Op

A _no-op_ is a function that does nothing. _No-op_ is short for _no operation_.

We commonly use _no-ops_ to avoid writing `if` statements. There's an example of this in the [Identity Function][Identity Function] glossary entry.

We're interested in the `if` statements that are used to work out if a function should be called or not:

```typescript
function myFunction(funcA: SomeFunctionType) {
    if (some expression) {
        funcA();
    } else {
        // do something else, because it isn't safe
        // to call funcA()
    }
}
```

We don't need the `if` statement if it's always safe to call `funcA()`. That's where the _no-op_ comes in.

* We design `funcA()` so that it's possible to create a _no-op_ for it.
* Then it's up to the [caller][Caller] to pass in either a function that does something, or the _no-op_.

Our function don't care either way. It doesn't need to care.

```typescript
function myFunction(funcA: SomeFunctionType) {
    funcA();
}
```

We've eliminated the `if` statement. That makes the code smaller, and makes our unit tests smaller, because we've eliminated complexity.

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
[Identity Function]: ./identity-function.md
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
