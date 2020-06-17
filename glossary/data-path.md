# Data Path

A _data path_ is a _dot.notation.path_ that describes how to navigate through a nested data structure.

It's a `string` that we use in Errors (and log messages!) to tell people which part of a data structure the Error / message is about.

For example:

```typescript
const exampleData = {
    schema: {
        invoice: {
            type: "object",
            properties: {
                currency: {
                    type: "string"
                },
                billTo: {
                    "$ref": "#/schema/identity",
                },
                lineItems: {
                    anyOf: [
                        {
                            "$ref": "#/schema/lineItem"
                        },
                        {
                            "$ref": "#/schema/creditNote"
                        }
                    ]
                }
            },
            requiredProperties: [ "currency", "billTo" ]
        }
    }
};
```

TypeScript Path                                            | Data Path
-----------------------------------------------------------|------------
`exampleData`                                              | `.`
`exampleData.schema.invoice`                               | `.schema.invoice`
`exampleData.schema.invoice.properties.lineItems.anyOf[0]` | `.schema.invoice.properties.lineItems.anyOf[0]`

As a rule, _data paths_ start with a `.`. (We say that the `.` refers to the _root object_ of the data structure.)

Some functions don't need to know their input value's data path, but they do call functions that require a data path of some kind. We use the `DEFAULT_DATA_PATH` for this. It has the special value of `input`.

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
