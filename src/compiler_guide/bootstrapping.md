# Bootstrapping

This document explains how VioletScript should be implemented in VioletScript.

### `Span` and `TokenData`

`com.violetscript.parser.source.Span`, a `Value` class, should contain:

- `script:Script`
- `start:StringIndex`
- `end:StringIndex`
- `firstLine:Int`
- `lastLine:Int`

The following are derived from the script using the fields above:

- `firstColumn:Int` zero based first column
  - `firstLineStartUTF8 = span.script.getLineStartUTF8(span.firstLine)`
  - `firstColumn = span.script.source.utf8IndexToIndex(span.start.utf8, {initialIndexUTF8: firstLineStartUTF8, initialIndex: 0})`
- `lastColumn:Int` zero based last column
  - `lastLineStartUTF8 = span.script.getLineStartUTF8(span.lastLine)`
  - `lastColumn = span.script.source.utf8IndexToIndex(span.end.utf8, {initialIndexUTF8: lastLineStartUTF8, initialIndex: 0})`

`com.violetscript.parser.tokenizer.TokenData` should contain similiar fields.

DISCARDED IDEAS:

- Physical: `endUTF8:Int`
- Virtual: `end:StringIndex` (derived from `script`, `start.utf8` and `start.default`)
  - `endDefault = span.script.source.utf8IndexToIndex(span.endUTF8, {initialIndexUTF8: span.start.utf8, initialIndex: span.start.default})`
  - `end = {#default: endDefault, utf8: endUTF8}`