# Side Effects

_Side effects_ are unintentional consequences of actions. That might mean:

* something that happened at runtime that you didn't expect, or
* a knock-on effect from changing the source code

_Side effects_ can cause [correctness][CORRECTNESS] and [robustness][ROBUSTNESS] issues, because they're not meant to happen.

It's best illustrated with an example:

```typescript
type MediaTypeOptions = OnErrorOptions;
type ContentTypeOptions = MediaTypeOptions;

function makeMediaType(
    input: string,
    { onError = THROW_THE_ERROR }: MediaTypeOptions,
    ... fnOpts: FunctionalOption<MediaType>
): MediaType;

function makeContentType(
    input: string,
    { onError = THROW_THE_ERROR }: ContentTypeOptions,
    ... fnOpts: FunctionalOption<ContentType>
): ContentType;
```

Here, we've got two [type aliases][Type Alias] for [user-supplied options][User-Supplied Options]:

* `MediaTypeOptions` are for RFC-compliant media types, and
* `ContentTypeOptions` are for the `text/html` bit of a full media type

and we have two corresponding [smart constructors][Smart Constructor]: `makeMediaType()` and `makeContentType()`.

Imagine we ship that, and everyone starts using it.

Let's say six months have passed, and [end-users][End-User] are complaining. They want to be able to set the character set of a new `MediaType`.

This is how NOT to do it:

```typescript
// in response to end-user complaints,
// we have added `charset` as an option
type MediaTypeOptions = OnErrorOptions & {
    charset?: string;
};

// in a pull-request, this line of code will
// appear unchanged. But we HAVE changed
// the definition of `ContentTypeOptions`.
type ContentTypeOptions = MediaTypeOptions;

// `makeMediaType()` now applies a default option
// every time it is called
//
// this make break existing code
function makeMediaType(
    input: string,
    {
        onError = THROW_THE_ERROR,
        charset = "UTF-8"
    }: MediaTypeOptions,
    ... fnOpts: FunctionalOption<MediaType>
): MediaType;

// `makeContentType()` will appear unchanged
// in a pull-request, but it has changed
function makeContentType(
    input: string,
    { onError = THROW_THE_ERROR }: ContentTypeOptions,
    ... fnOpts: FunctionalOption<ContentType>
): ContentType;

```

Adding an extra field to `MediaTypeOptions` has introduced (at least!) two _side effects_:

* We haven't just changed the options that `makeMediaType()` accepts. We've also changed the options that `makeContentType()` accepts. That's not what we intended. That's a _side effect_.
* We've forced `makeMediaType()` to always set a `charset` parameter. That's another _side effect_.

What are the consequences of these _side effects_?

* `ContentTypeOptions` is not longer accurate. Anyone who reads it will believe that they can pass a `charset` option into `makeContentType()`.
* `makeContentType()` won't barf if they do ... it'll just ignore the option completely. It'll look like a silent error if anyone tries to use the new option there.
* The [end-user][End-User] will waste time wondering why the option isn't working. Then they might waste your time by filing a bug report about it.
* Worse still, they might think your code is too buggy to trust, and they might stop using it entirely.
* `makeMediaType()` now always sets a `charset`. That breaks backwards-compatibility. It will probably break someone's existing code.

In this example, the correct way to solve this problem is to create a suitable [functional option][User-Supplied Functional Options]:

```typescript
// our two types DO NOT CHANGE
// from the original definition
type MediaTypeOptions = OnErrorOptions;
type ContentTypeOptions = MediaTypeOptions;

// our two smart constructors DO NOT CHANGE
// from the original definition
function makeMediaType(
    input: string,
    { onError = THROW_THE_ERROR }: MediaTypeOptions,
    ... fnOpts: FunctionalOption<MediaType>
): MediaType;

function makeContentType(
    input: string,
    { onError = THROW_THE_ERROR }: ContentTypeOptions,
    ... fnOpts: FunctionalOption<ContentType>
): ContentType;

// our MediaType changes, because it's a
// convenient place to stash our new
// functional option
class MediaType {
    // the rest of implementation isn't import
    // for this example

    // this is a functional option
    static public buildSetCharset(charset: string): FunctionalOption<MediaType> {
        return (input: MediaType): MediaType => {
            // `parse()` returns an object with
            // the different parts of the MediaType
            // in separate fields
            const parts = input.parse();

            // we update one of those fields
            parts.parameters['charset'] = charset;

            // we build a BRAND NEW MediaType
            // and return it
            return MediaType.fromParts(parts);
        }
    }
}

// we can now pass our functional option in
// when we make the media type
const myMediaType = new MediaType(
    res.headers["content-type"],
    {},
    MediaType.buildSetCharset("us-ascii")
);

// and if we want to change the charset of an
// existing `MediaType`, that's easy too
//
// this is only safe because we've avoided
// a second side effect
const betterMediaType = MediaType.buildSetCharset("UTF-8")(myMediaType);
```

At first glance, this looks like a heavy-handed way to do this. Parsing the contents of a `MediaType` is going to incur a runtime cost, no matter how fast our parser is.

It's worth it, because this code completely avoids all of the _side effects_ we listed earlier on, and _more_!

* We don't accidentally change the definition of _ContentTypeOptions_,
* `makeMediaType()` is no longer forced to set the `charset` parameter all the time,
* At runtime, in the function created by `MediaType.buildSetCharset()`, we don't change the `charset` parameter of the input `MediaType` parameter. We treat that input parameter as [immutable][Immutability].

Not only do we save time and frustration when the [end-user][End-User] is writing their code, we prevent surprises in production when data mysteriously gets corrupted.

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
