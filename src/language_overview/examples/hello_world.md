# Hello World

Here is a program that prints a message "Hello, world!" to the console:

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