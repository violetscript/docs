# Decorators

A decorator is a function that either returns `void` or returns another function that returns `void`, applied to either a type, property or method as expressions enclosed by square brackets. Decorators cannot be applied everywhere.

`[D(x = 10)]` is equivalent to `[D({x: 10})]`.

## Decorators Applied to Types

```
function MyTypeDecorator(type:Class):void {
}

[MyTypeDecorator]
class C {
}
```

## Decorators Applied to Properties

```
function MyFieldDecorator(o:C, {name}:DecoratorProperty):void {
    trace(name);
}

class C {
    [MyFieldDecorator]
    public var x:Number;
}
```

## Decorators Applied to Methods

```
function MyMethodDecorator(o:C, name:String):void {
    trace(name);
}

class C {
    [MyMethodDecorator]
    public function f():void {
    }
}
```

## Reserved Lexical Decorators

The following decorators are reserved, but can still be used if they do not directly appear as lexical references:

- When applied to a class definition, `[Value]` is reserved
- When applied to an enum definition, `[Flags]` is reserved