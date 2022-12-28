# Proxies

VioletScript supports proxies to alter the behavior of certain operations. Currently, only `class` and `enum` can define proxies; `interface` cannot define proxies.

## Conversion Proxies

These proxies do not enable use of the literal `this`.

```
class C {
    proxy function convertImplicit(a:T):C? {
        // implicit conversion from A to C
    }

    proxy function convertExplicit(a:T):C? {
        // explicit conversion from A to C
    }
}
```

## Unary Operator Proxies

These proxies do not enable use of the literal `this`.

```
class C {
    // +o;
    proxy function positive(a) ...;

    // -o;
    proxy function negate(a) ...;

    // ~o;
    proxy function bitNot(a) ...;
}
```

## Binary Operator Proxies

These proxies do not enable use of the literal `this`.

```
class C {
    // a === b;
    proxy function equals(a, b) ...;

    // a !== b;
    proxy function notEquals(a, b) ...;

    // a < b;
    proxy function lt(a, b) ...;

    // a > b;
    proxy function gt(a, b) ...;

    // a <= b;
    proxy function le(a, b) ...;

    // a >= b;
    proxy function ge(a, b) ...;

    // a + b;
    proxy function add(a, b) ...;

    // a - b;
    proxy function subtract(a, b) ...;

    // a * b;
    proxy function multiply(a, b) ...;

    // a / b;
    proxy function divide(a, b) ...;

    // a % b;
    proxy function remainder(a, b) ...;

    // a ** b;
    proxy function pow(a, b) ...;

    // a & b;
    proxy function bitAnd(a, b) ...;

    // a ^ b;
    proxy function bitXor(a, b) ...;

    // a | b;
    proxy function bitOr(a, b) ...;

    // a << b;
    proxy function leftShift(a, b) ...;

    // a >> b;
    proxy function rightShift(a, b) ...;

    // a >>> b;
    proxy function unsignedRightShift(a, b) ...;
}
```

## Index Proxies

These proxies enable use of the literal `this`.

```
class C {
    // o[i];
    proxy function getIndex(i:I):V (
        ...
    );

    // o[i] = v;
    proxy function setIndex(i:I, v:V) {
        ...
    }

    // delete o[i];
    proxy function deleteIndex(i):Boolean {
    	...
    }

    // v in o;
    proxy function has(v):Boolean (
    	...
    );
}
```

## Iteration Proxies

These proxies enable use of the literal `this`.

```
class C {
    // for..in
    proxy function iterateKeys():Generator.<K> {
        // yield
    }

    // for each
    proxy function iterateValues():Generator.<V> {
        // yield
    }
}
```