# Functions

```
function f():void {
}

function fr(a:Number):void {
}

function fo(a:Number = 10):void {
}

function fRest(...a:[Number]):void {
}

function fExpBody():String (
	'violetscript'
);

// throws clause is used for documentation purposes
function fThatThrows():void throws RangeError {
}
```

## Generators

```
function f():Generator.<Number> {
	yield 10;
}
```

## Asynchronous Functions

```
function f():Promise.<Number> {
	await a();
	return 10;
}
```