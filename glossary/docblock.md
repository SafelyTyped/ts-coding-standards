# Docblock

A _docblock_ is a comment immediately preceeding the definition of a type or value.

Tools like Typedoc can auto-generate reference documentation from the contents of your _docblocks_.

Normal comments start with `//` on every line. Docblocks start with a `/**` so that the tools can tell them apart from regular comments.

Here's an example:

```typescript
/**
 * ValueObject is the base class for defining your Value Object
 * hierarchies.
 *
 * Every Value Object:
 *
 * - has a stored value
 * - that you can get the valueOf()
 *
 * We've deliberately kept this as minimal as possible. We're looking to
 * support idiomatic TypeScript code, rather than functional programming.
 *
 * If you do want fully-functional programming, use one of the many
 * excellent libraries that are out there instead.
 *
 * Use {@link EntityObject} for data that has an identity (a primary key).
 *
 * @category Archetypes
 * @template T the type that's wrapped by this class
 */
export class ValueObject<T> implements Value<T> {
    /**
     * value is the data that we wrap.
     *
     * Child classes are welcome to access it directly (to avoid the cost
     * of a call to `valueOf()`), but must never modify the data at all.
     *
     * @returns the data that is stored in this object.
     */
    protected readonly value: T;

    /**
     * Constructor builds a new ValueObject.
     *
     * @param input the data to store in this object.
     */
    protected constructor(input: T) {
        this.value = input;
    }

    /**
     * valueOf() returns the wrapped value.
     *
     * For types passed by reference, we do NOT return a clone of any kind.
     * You have to be careful not to accidentally change this value.
     *
     * @returns the data that is stored in this object.
     */
    public valueOf(): T {
        return this.value;
    }

    /**
     * implementsValue() is a helper method for the {@link isValue} type guard
     * function.
     */
    public implementsValue(): this is Value<T> {
        return true;
    }
}
```

At the time of writing, there isn't a single, well-supported standard for writing _docblocks_ for Typescript.

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
