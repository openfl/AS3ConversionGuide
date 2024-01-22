# Overview

## Declaring a Class

Haxe and ActionScript 2.0 follow a similar structure when declaring a new class. Similar to ActionScript 2.0, `package` is optional if a class file is located in the top-level of a source directory, but the package must match the file path if it is used in a sub-directory.

The constructor function in Haxe is called `new`, while in ActionScript, it matches the class name. Declaring `public` on a constructor in optional in Haxe, and `private` constructors are supported (unlike ActionScript).

### ActionScript 2.0

```haxe
package;

class Test {
    
    function Test () {
        
    }
    
}
```

### ActionScript 3.0

```ActionScript
package {
    
    public class Test {
        
        public function Test () {
            
        }
        
    }
    
}
```

### Haxe

```haxe
package;

class Test {
    
    public function new () {
        
    }
    
}
```

## Core Types

In ActionScript 2.0 the core data types are capitalized. Haxe follows this pattern, and goes further to specify that _all package names must be lowercase, and all types must start with an uppercase letter_ (such as "com.example.ClassName").

Haxe uses `Float` and `Int` as core types, which are similar to `Number` and `int` in ActionScript. Haxe uses `Dynamic` to describe a wildcard type, similar to the ActionScript `*` type, and close to the ActionScript `Object` type.

### ActionScript 2.0

```haxe
String
Number
Boolean
Object
Void
```

### ActionScript 3.0

```ActionScript
String
Number
int
Boolean
String
Object
void
```

### Haxe

```haxe
String
Float
Int
Bool
Dynamic
Void
```

## Property Access

Haxe expands upon the `get`/`set` functionality of ActionScript to provide nuanced property access support. For example, a read-only variable can be declared without a getter and an extra variable.

When defining a getter or a setter function, Haxe requires the "get\_" or "set\_" prefix. This helps reflection work more easily, and ensures consistent behavior, even on environments that do not support getters and setters natively.

Note in these examples how in Haxe you can generate a default getter or setter by using the `default` keyword in a property declaration. 

### ActionScript 3.0

```ActionScript 
private var _customSetter:String;
private var _readOnly:Number;

public get function customSetter ():String {
    
    return _customSetter;
    
}

public set function customSetter (value:String):void {
    
    _customSetter = value + "!";
    
}

public get function readOnly ():Number {
    
    return _readOnly;
    
}
```

### Haxe

```haxe
public var customSetter (default, set):String;
public var readOnly (default, null):Float;

private function set_customSetter (value:String):String {
    
    return this.customSetter = value + "!";
    
}
```

## Namespaces

ActionScript 3.0 supports namespaces, both `public` and `private` (similar to ActionScript 2.0) in addition to `internal`, `protected` or custom namespaces. Haxe supports only `public` and `private` (with `private` behaving similar to ActionScript's `protected` namespace) and does not support custom namespaces.

However, Haxe does support access control using meta-data tags such as `@:allow` and `@:access` for `private` access. 

### ActionScript 3.0

```ActionScript
package {
    
    public class Test {
        
        internal static var hello:String = "Hello";
        
    }
    
}
```
```ActionScript
package {
    
    public class Test2 {
        
        public function Test2 () {
            
            var msg:String = Test.hello;
            
        }
        
    }
    
}
```

### Haxe

```haxe
class Test {
    
    private static var hello:String = "Hello";
    
}
```
```haxe
@:access(Test)
public class Test2 {
    
    function new () {
        
        var msg = Test.hello;
        
    }
    
}
```

## Type Inference

Declaring the type for a variable is optional in ActionScript 2.0, but required when statically typing variables in ActionScript 3.0. This enables faster performance by knowing the type of a variable at compile-time.

Haxe supports compiler type inference, a valuable feature that allows you to eliminate boiler-plate code, while enjoying the benefits of static typing. It is also possible to add type declarations similar to ActionScript.

### ActionScript 3.0

```ActionScript
var hello:String = "World";
var fruit:Array = [ "apple", "orange" ];
```

### Haxe

```haxe
var hello:String = "World";
var fruit:Array<String> = [ "apple", "orange" ];
```

_or_

```haxe
var hello = "World";
var fruit = [ "apple", "orange" ];
```

## Loops

ActionScript has multiple kinds of loops. There are `for ... in` loops, `for ... each` loops and `for` loops. Haxe simplifies this syntax to a single `for ... in` loop. To iterate over keys instead of values, use `Reflect.fields` for anonymous objects, or `.keys()` for maps. Both ActionScript and Haxe support `while` loops. If your loop is not a simple iteration, you must use a `while` loop in Haxe. ActionScript loop variables are visible outside the loop, while Haxe loop variables are not. 

### ActionScript 3.0

```ActionScript
for (var i:uint = 0; i < 10; i++) {
    
    trace (i);
    
}

var array:Array = [ "a", "b", "c" ];

for each (var value:String in array) {
    
    trace (value);
    
}

for (var j:int = 30; j>=0; j--) {
    
    trace (j--);
    
}
trace("final j:"+j);
```

### Haxe

```haxe
for (i in 0...10) {
    
    trace (i);
    
}

var array = [ "a", "b", "c" ];

for (value in array) {
    
    trace (value);
    
}

var j:Int = 30;

while (j >= 0) {
    
    trace(j--);
    j--;
    
}
trace ("final j:"+j );
```
