# Enumeration Types

Enumeration types define variants with an unique number and an unique String.

The following example program defines an enumeration with four constants:

```
enum ExampleEnum {
	const VARIANT_A;
	const VARIANT_B = 'customizedName';
	const VARIANT_C = 64;
	const VARIANT_D = ['anotherCustomizedName', 10];
}

ExampleEnum.VARIANT_A.valueOf() == 0;
ExampleEnum.VARIANT_A.toString() == 'variantA';

ExampleEnum.VARIANT_B.valueOf() == 1;
ExampleEnum.VARIANT_B.toString() == 'customizedName';

ExampleEnum.VARIANT_C.valueOf() == 64;
ExampleEnum.VARIANT_C.toString() == 'variantC';

ExampleEnum.VARIANT_D.valueOf() == 10;
ExampleEnum.VARIANT_D.toString() == 'anotherCustomizedName';
```

## Custom Properties

The block of an `enum` definition can contain anything, as the following program demonstrates:

```
enum E {
	function f():void {
	}
}
```

## Type Inference

Wherever a value of an `enum` is expected, a string literal can be used. In addition, for flags enumerations, an object initializer, array initializer or `undefined` can also be used.

```
var e:ExampleEnum = ExampleEnum.VARIANT_A;
var e:ExampleEnum = 'variantA';

var f:ExampleFlags = undefined;
var f:ExampleFlags = {};
var f:ExampleFlags = [];
```

## Flags

Flags enumerations, prefixed with the special `Flags` decorator, define combinatory variants. A variant number is either 1 or power of two.

```
[Flags]
enum ExampleFlags {
	const FLAG_A; // 1
	const FLAG_B; // 2
	const FLAG_C; // 4
}

var f:ExampleFlags = ['flagA'];
var q:ExampleFlags = {flagB: true};

f += 'flagC';
f -= 'flagC';
f = f.toggle('flagC');
f = f.filter('flagC');
'flagC' in f;

// returns an ExampleFlags with all flags present
ExampleFlags.all;
```