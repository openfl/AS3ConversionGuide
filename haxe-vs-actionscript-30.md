# Comparing Haxe and ActionScript

Since the Haxe programming language originated from an ActionScript 2.0 compiler, there are many similarities between the languages. In fact, a number of the minor differences between ActionScript 3.0 and Haxe can be explained if you understand this heritage.

## Core Data Types

When typing a method or a variable, these are some of the core types in each language:

### ActionScript 2.0

```as2
String
Number
Boolean
Object
Void
```

### ActionScript 3.0

```as3
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

ActionScript 2.0 is consistent in capitalizing these core types, but is missing some core types that are important to statically-typed language, such as distinguishing integers from floating point numbers. ActionScript 3.0 is more expressive, but uses a mixture of capitalized and uncapitalized names for core types, which is a bit confusing.

Haxe enforces consistent capitalization for types, and varies slightly from ActionScript in how some core types are named, more closely resembling other languages. `Float` and `Int` is arguably a better combination than `Number` and `int`. Haxe also uses `Bool` instead of `Boolean` (similar to C/C++) and uses `Dynamic` to describe a dynamic (untyped) value.

## Defining a Class



#### ActionScript 2.0

```as2
package example;

class MyClass {
    
    function MyClass () {
        
        
    }

}
```

#### ActionScript 3.0

```as3
package example {
    
    public class MyClass {
        
        public function MyClass () {
            
            
        }

    }

}
```

#### Haxe

```haxe
package example;

class MyClass {
    
    function new () {
        
        
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
