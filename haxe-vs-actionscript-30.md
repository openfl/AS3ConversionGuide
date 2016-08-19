# Comparing Haxe and ActionScript

Since the Haxe programming language originated from an ActionScript 2.0 compiler, there are many similarities between the languages. In fact, a number of the minor differences between ActionScript 3.0 and Haxe can be explained if you understand this heritage.

## Creating a Class

#### ActionScript 2.0

```as2
package example;

class MyClass {
    
    public var publicBoolean:Boolean;
    private var privateString:String;
    var number:Number;
    
    function MyClass () {
        
        var boolean = true;
        var string:String = "Hello";
        
    }

}
```

#### ActionScript 3.0

```as3
package example {
    
    public class MyClass {
        
        public var publicBoolean:Boolean;
        private var privateString:String;
        private var number:Number;
        
        public function MyClass () {
            
            var boolean:Boolean = true;
            var string:String = "Hello";
            
        }

    }

}
```

#### Haxe

```haxe
package example;

class MyClass {
    
    public var publicBoolean:Boolean;
    private var privateString:String;
    var number:Number;
    
    function new () {
        
        var boolean = true;
        var string:String = "Hello";
        
    }
    
}
```

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
