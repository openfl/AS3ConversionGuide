# Class Declarations

You can see more similarities with ActionScript 2.0 when you consider how classes are defined:

### ActionScript 2.0

```haxe
package example;

class MyClass {
    
    function MyClass () {
        
        
    }

}
```

### ActionScript 3.0

```ActionScript
package example {
    
    public class MyClass {
        
        public function MyClass () {
            
            
        }

    }

}
```

### Haxe

```haxe
package example;

class MyClass {
    
    function new () {
        
        
    }
    
}
```

ActionScript 2.0 did not require package declarations, as packages themselves were optional. ActionScript 3.0 requires the use of classes, and requires that classes are organized into packages.

Similar to ActionScript 3.0, Haxe also requires that class files are organized into matching files, but the `package` declaration is optional if the code is not organized in a subdirectory. Similar to ActionScript 2.0, declaring the class or the constructor as `public` is not needed, because these are implied.

Haxe distinctly requires that class constructors are called `new` instead matching the class name.
