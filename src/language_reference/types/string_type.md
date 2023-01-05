# String Type

The String type is UTF-8 encoded. All methods are aware of Unicode Code Points, which means a Code Point access may be inefficient in large strings depending on what the programmer uses as index:

- Indexing a String with an `Int` internally iterates the string UTF-8 content until the Code Point index is reached.
- Indexing a String with a `StringIndex` object goes straight to the character. A `StringIndex` is result of different operations such as `indexOf()`.

The String type can also be indexed with a `GraphemeIndex`.