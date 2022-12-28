# Packages

A package is a namespace reusable by other scripts. The following program demonstrates basic use of `package` definitions:

```
package {
	// global package
	public const globalX:Number = 10;
}
package com.qux.bar {
	public function f():void {
	}
	public function q():void {
	}
}

globalX;
global.globalX; // equivalent

com.qux.bar.f();
com.qux.bar.q();
global.com.qux.bar.f();

// open com.qux.bar in lexical scope
{
	import com.qux.bar.*;
	f();
}
```