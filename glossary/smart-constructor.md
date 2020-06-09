# Smart Constructor

A _smart constructor_ is a function that creates safe types.

* It calls one or more [data guarantees][Data Guarantee] to validate its inputs.
* It rejects any input data that isn't within the range / specification of the safe type.

For example:

```typescript
class MediaType extends ValueObject<string> {
    // this is a smart constructor
    public constructor(input: string) {
        // if `input` doesn't conform to the RFC spec
        // for a MediaType, it throws an Error
        mustBeMediaTypeData(input);

        // at this point, we know it's safe
        super(input);
    }
}
```

Despite the name, a _smart constructor_ doesn't have to be a _class constructor_. It can be any function that creates types:

```typescript
type Uuid = Branded<string, "@safelytyped/uuid">;

// `makeUuid()` is a smart constructor too
function makeUuid(input: string): Uuid {
    mustBeUuidData(input);
    return input as Uuid;
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
