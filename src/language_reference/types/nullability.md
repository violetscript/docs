# Nullability

The only type that by default includes `undefined` and `null` is `*`, the dynamic type. An union type can be formed to include these values. The type expression `T?` is equivalent to the union `null|T`. The type expression `T!` escapes `T` from `null` and `undefined`.

The postfix operator `!`, as in `o!`, unwraps from an union with `null`, `undefined` or both.