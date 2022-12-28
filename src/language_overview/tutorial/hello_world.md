# Hello World

Here is a Hello World program using a separate function:

```
function greet(noun:String):void {
	trace('Hello, $noun!'.apply({noun}));
}
greet('world!');
```