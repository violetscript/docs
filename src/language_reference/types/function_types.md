# Function Types

Function types inherit the Function class.

```
// parameterless
type F1 = ()->void;

// with required parameter
type F2 = (a:Number)->void;

// with optional parameter
type F3 = (a?:Number)->void;

// with rest parameter
type F4 = (...a:[Number])->void;
```