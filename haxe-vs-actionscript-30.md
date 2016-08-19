# Comparing Haxe and ActionScript

Since the Haxe programming language originated from an ActionScript 2.0 compiler, there are many similarities between the languages. In fact, a number of the minor differences between ActionScript 3.0 and Haxe can be explained if you understand this heritage. Consider the following:

#### ActionScript 2.0

```as2
package example;

class MyClass {
    
    public var publicBoolean:Boolean;
    private var privateString:String;
    var privateNumber:Number;
    
    function MyClass () {
        
        var localBoolean = true;
        var localString:String = "Hello";
        
    }

}
```

#### ActionScript 3.0

```as3
package example {
    
    public class MyClass {
        
        public var publicBoolean:Boolean;
        private var privateString:String;
        private var privateNumber:Number;
        
        public function MyClass () {
            
            var localBoolean:Boolean = true;
            var localString:String = "Hello";
            
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
    var privateNumber:Number;
    
    function new () {
        
        var localBoolean = true;
        var localString:String = "Hello";
        
    }
    
}
```
