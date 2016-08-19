# Variable Declarations

## Class Properties

### ActionScript 2.0

```haxe
package example;

class MyClass {
    
    public static var a:String;
    private var b:Number;
    var c:Boolean;
    
    function MyClass () {
        
        
    }
    
}
```

### ActionScript 3.0

```ActionScript
package example {
    
    public class MyClass {
        
        public static var a:String;
        private var b:Number;
        private var c:Boolean;
        
        public function MyClass () {
            
            
        }
        
    }
    
}
```

### Haxe

```haxe
package example;

class MyClass {
    
    public static var a:String;
    public var b:Float;
    var c:Bool;
    
    function new () {
        
        
    }
    
}
```

Declaring class properties is similar between ActionScript 2.0, ActionScript 3.0 and Haxe, but in Haxe and ActionScript 2.0 the `private` declaration is optional. 

## Local Variables

ActionScript 1.0 and 2.0 were based on a dynamic virtual machine, which, while expressive, had serious performance limitations. ActionScript 3.0 introduced support for static types, which improves runtime performance considerably.

### ActionScript 2.0
```haxe
var hello = "World";
var answer:Number = 42;
```

### ActionScript 3.0

```ActionScript
var hello:String = "World";
var answer:int = 42;
```

### Haxe

```haxe
var hello = "World";
var answer:Int = 42;
```

The unfortunate side-effect of static types in ActionScript 3.0 is that it forces it upon the user whenever a variable is declared.

Haxe supports _type inference_, which allows the compiler to _infer_ a type when no type is declared. In the above sample, the `hello` variable will be statically typed as a `String`. This has the same performance benefits as ActionScript 3.0, but can lead to simpler code.

## Constants

### ActionScript 2.0

_ActionScript 2.0 does not support constants._ 

### Actionscript 3.0

```ActionScript
public const gravity:Number = 9.8;
```

### Haxe

```haxe
public inline static var gravity = 9.8;
```

Haxe avoids the use of a `const` keyword, instead using the existing `static` and `inline` variables to define a constant.

## Property Access

### ActionScript 2.0 and 3.0

```haxe
private var _customValue:Number;
private var _readOnly:String;

public function get readOnly ():String {
    
    return _readOnly;
    
}

public function get customProp ():Number {
    
    return _customValue;
    
}

public function set customProp (value:Number):Void {
    
    _customValue = value;
    
}
```

### ActionScript 3.0

```ActionScript
private var _customValue:int;
private var _readOnly:String;

public function get readOnly ():String {
    
    return _readOnly;
    
}

public function get customProp ():int {
    
    return _customValue;
    
}

public function set customProp (value:int):void {
    
    _customValue = value;
    
}
```

### Haxe

```haxe
public var customValue(get, set):Int;
public var readOnly(default, null):String;

private var _customValue:Int;

private function get_customValue ():Int {
    
    return _customValue;
    
}

private function set_customValue (value:Int):Int {
    
    return _customValue = value;
    
}
```

ActionScript 2.0 and 3.0 support read-only variables through the use of a getter method, but Haxe has built-in support for controlling property access, reducing boiler-plate code.

All three languages allow the use of custom getter and setter functions, the syntax varies because many target environments do not support get/set properties, only "get\_" and "set\_" functions.
