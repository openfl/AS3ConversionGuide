# Data Types

ActionScript 3.0 (in "strict mode") and Haxe both use _strict data types_. This allows the compiler to make certain assumptions on how data will be used and accessed, improving performance, and usually improving how easy it is to write and maintain the code as well.

Each language is somewhat different in the core data types they support, but understanding one should make it simple to learn the other.

## Primitives

ActionScript 3.0 has the following primitive value data types:

 * `String`
    
    A text value, such as a name or a written message
    
 * `Number`
    
    Any numeric value (integer or floating point)
    
 * `int`
    
    An integer numeric value (a whole/round number). This can be positive or negative
    
 * `uint`
    
    An unsigned integer numeric value. This is similar to `int`, but it is always positive
    
 * `Boolean`
    
    A true or false value
    
Haxe has the following primitive value data types:
    
 * `String`
    
    A text value, such as a name or a written message
    
 * `Float`
    
    Any numeric value (integer or floating point)
    
 * `Int`
    
    An integer numeric value (a whole/round number). This can be positive or negative
    
 * `Bool`
    
    A true or false value
    
Haxe has a `UInt` abstract type. Though it is not a primitive data type, it can be used to interpret an `Int` as an unsigned value. `Int` is most commonly used in Haxe projects, but `UInt` is available when desired.

## Complex Values

As a virtual machine, ActionScript defines a set of data types that store complex values. These include `Object`, `Array`, `Date`, `Error`, `Function`, `RegExp`, `XML` and `XMLList`.

The Haxe standard library includes similar data types, such as `Dynamic`, `Array`, `Date`, `EReg` and `Xml`. Most of the core data types are composed out of Haxe language features such as classes, enums, abstracts and externs.

In ActionScript 3.0, every value (whether primitive or complex) is an `Object`. In Haxe, the `Dynamic` type can be used to describe any type.

In ActionScript 3.0 and Haxe, you can define an array using array literal syntax, or by using an array constructor.

```haxe
var list = [ 1, 2, 3 ];
var list2 = new Array<Int> ();
```

The ActionScript core `Array` type is dynamic. This means that the `Array` type will allow any kind of value in the same object:

```ActionScript
var list:Array = [ 1, "2", false ];
```

For better performance, and more nuanced control over code, Haxe arrays are _statically typed_, which means that it accepts only values of one type by default, unless it is a dynamic array.

```haxe
var mixed:Array<Dynamic> = [ 1, "2", false ];
var integers:Array<Int> = [ 1, 2, 3];
```

Haxe does not include a core `Error` type, but allows errors to be thrown of any type

```haxe
if (error) {
    
    throw "Something bad happened!";
    
}
```
