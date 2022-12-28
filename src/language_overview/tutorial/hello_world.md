# Hello World

Here is a basic Hello World program:

```
trace('Hello, world!');
```

Here is one with a separate function:

```
function greet(noun:String):void {
	trace('Hello, $noun!'.apply({noun}));
}

greet('world');
```