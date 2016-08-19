# Comparing Haxe and ActionScript

Since the Haxe programming language originated from an ActionScript 2.0 compiler, there are many similarities between the languages. In fact, a number of the minor differences between ActionScript 3.0 and Haxe can be explained if you understand this heritage.


## Defining a Class

You can see more similarities with ActionScript 2.0 when you consider how classes are defined:

### ActionScript 2.0

```as2
package example;

class MyClass {
    
    function MyClass () {
        
        
    }

}
```

### ActionScript 3.0

```as3
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

## Declaring Variables and Methods

### ActionScript 2.0

```as2
package example;

class MyClass {
    
    public var a:String;
    private var b:Number;
    var c:Boolean;
    
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
        
        public var a:String;
        private var b:Number;
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
    
    public var a:String;
    private var b:Float;
    var c:Bool;
    
    function new () {
        
        var hello = "World";
        var answer:Float = 42;
        
    }
    
}
```

asf


sadfasfasdf

ActionScript 2.0 does not require packages, but making packages optional can make it difficult to find code. ActionScript 3.0 requires packages, and requires that each file matches the name of the primary class 


## Declaring a Package

In ActionScript 2.0, packages were optional. Although this lent itself to flexibility, this can make finding code difficult in large projects.

ActionScript 3.0 made packages a requirement, as well as requiring that each primary class was stored in a file that matched its package and class name.  

Haxe requires distinct (and properly) named files, similar to ActionScript 3.0, 

sure that classes were stored in files that matched 



packages were optional, similar to JavaScript, but when ActionScript 



ActionScript 2.0 packages were optional

ActionScript (similar to JavaScript) is a dynamic language. ActionScript 2.0 provided optional support for type information. The "package" declaration, the "public" and "private" designations on a class, variable or method, and the ":Type" information on local variables were optional.

ActionScript 3.0, although still dynamic, tried to become more static in order to improve performance. The above designations became required.

\
