# Variable Declarations

Fundamentally, ActionScript is dynamic. In ActionScript 2.0, type declarations were optional hints to help developers write better code, but had no impact on the runtime performance of a project. Although ActionScript 3.0 (and AVM2) is still dynamic, ActionScript 3.0 does have some support for static types, which is expressed by _always_ requiring type information.

### ActionScript 2.0

```haxe
package example;

class MyClass {
    
    public static var a:String;
    public var b:Number;
    private var c:Boolean;
    
    function MyClass () {
        
        var hello = "World";
        var answer:Number = 42;
        
    }
    
}
```

### ActionScript 3.0

```as3
package example {
    
    public class MyClass {
        
        public static var a:String;
        public var b:Number;
        private var c:Boolean;
        
        public function MyClass () {
            
            var hello:String = "World";
            var answer:Number = 42;
            
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
    private var c:Bool;
    
    function new () {
        
        var hello = "World";
        var answer:Float = 42;
        
    }
    
}
```

In these samples, there is little difference in how variables are declared. The most important difference above is in how the local variable "hello" is declared.

### ActionScript 2.0 and Haxe

```haxe
var hello = "World";
```

### ActionScript 3.0

```as3
var hello:String = "World";
```

ActionScript 2.0 does not require type information, so `var hello = "World";` is valid code. However, because the result is dynamically typed, the code will execute more slowly than in other languages.

In ActionScript 3.0, the compiler supports static types, but it requires the user to always give the compiler this information. Although this is good for performance, it is not as good from a user perspective.

Haxe supports _type inference_, which means that the compiler still uses static types, but it will _infer_ what that type is when you do not include that information. `var hello = "World";` means the compiler will infer that `hello` is a `String` type, and will not allow `hello` to be used differently.

You must type `hello` as `Dynamic` in order to store different kinds of values in the same variable, but this is uncommon and bad practice for fast code.

