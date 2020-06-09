# Identity Function

An _identity function_ is a function that returns the exact same value that it received as input:

```typescript
//
export const identity<T> = (x: T) => x;
```

They're more commonly seen in functional programming than in imperative programming.

In imperative programming, we mainly see them used as a [no-op][No-Op] when dealing with [mandatory dependencies][Mandatory Dependency].

For example:

```typescript
type TransformFn = (x: any) => string;

function normaliseToString(transform: TransformFn, input: any, ...normalisers: Identity<string>) {
    // our return value
    let retval = transform(input);

    // apply the normalisers (if we have any)
    normalisers.forEach((fn) => { retval = fn(retval); });

    // all done
    return retval;
}

// if we want to use `normaliseToString()` with a string,
// we would use the `identity()` function:
normaliseToString(identity, "HELLO WORLD", String.toLowerCase);
```

Without the identity function, we'd have to write an `if` statement instead:

```typescript
type TransformFn = (x: any) => string;

function normaliseToString(transform: TransformFn, input: any, ...normalisers: Identity<string>) {
    // our return value
    let retval: string;

    // make sure we have a string
    if (typeof input === string) {
        retval = input;
    } else {
        retval = transform(input);
    }

    // do the normalisation
    normalisers.forEach((fn) => { retval = fn(retval); });

    // all done
    return retval;
}
```

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
