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

When defining a getter or a setter function, Haxe requires the "get\_" or "set\_" prefix. This helps reflection work more easily, and ensures consisten behavior, even on environments that do not support getters and setters natively.

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
    
    public namespace custom_namespace;
    
}
```
```ActionScript
package {
    
    public class Test {
        
        custom_namespace static var hello:String = "Hello";
        
    }
    
}
```
```ActionScript
package {
    
    use namespace custom_namespace;
    
    public class Test2 {
        
        public function Test2 () {
            
            var msg:String = Test.custom_namespace::hello;
            
        }
        
    }
    
}
```

### Haxe

```haxe
class Test {
    
    private static var hello = "Hello";
    
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


