# Cheat Sheet

## Basic Types

### ActionScript 3

```ActionScript
Boolean
int
Number
Object
void
Array
Vector.<String>
```

### Haxe

```haxe
Bool
Int
Float
Dynamic
Void
Array<Dynamic>
Array<String>
```

## Package Declarations

### ActionScript 3

```ActionScript
package com.example.myapplication {
 
}
```

### Haxe

```haxe
package com.example.myapplication;
```

## Defining a Class

### ActionScript 3

```ActionScript
public class MyClass {
 
   public function MyClass () {
 
 
   }
 
}
```

### Haxe

```haxe
class MyClass {
 
   public function new () {
 
 
   }
 
}
```

## Loops

### ActionScript 3

```ActionScript
for (var i:uint = 0; i < 100; i++) {
 
}
 
for each (var value:String in items) {
 
}
 
for (var propertyName:String in object) {
 
}
```

### Haxe

```haxe
for (i in 0...100) {
 
}
 
for (value in items) {
 
}
 
var fields = Reflect.fields (object);
for (propertyName in fields) {
 
}
```

## Switch Statements

### ActionScript 3

```ActionScript
switch (value) {
 
   case 1:
      trace ("Equal to 1");
      break;
 
   default:
      trace ("Not equal to 1");
      break;
 
}
```

### Haxe

```haxe
switch (value) {
 
   case 1:
      trace ("Equal to 1");
 
   default:
      trace ("Not equal to 1");
 
}
```

## Type Inference

### ActionScript 3

```ActionScript
var hi = "Hello World";
 
// type is Object
// fails to compile in strict mode
```

### Haxe

```haxe
var hi = "Hello World";
 
// type is String
// even works for code completion
```

## Type Casting

### ActionScript 3

```ActionScript
var car:Car = vehicle as Car;
 
var toString:String = String (10);
var toNumber:Number = Number ("10");
var toInteger:int = int (10.1);
```

### Haxe

```haxe
var car:Car = cast vehicle;
 
// or for a safe cast:
 
var car = cast (vehicle, Car);
 
var toString = Std.string (10);
var toNumber = Std.parseFloat ("10");
var toInteger = Std.int (10.1);
```

## Type Details

### ActionScript 3

```ActionScript
if (vehicle is Car) {
 
}
 
import flash.utils.getDefinitionByName;
import flash.utils.getQualifiedClassName;
 
name = getQualifiedClassName (vehicle);
type = Class (getDefinitionByName (name);
```

### Haxe

```haxe
if (Std.is (vehicle, Car)) {
 
}
 
type = Type.getClass (vehicle);
name = Type.getClassName (type);
```

## Checking for Null

### ActionScript 3

```ActionScript
if (object == null) {
 
}
 
if (!object) {
 
}
```

### Haxe

```haxe
if (object == null) {
 
}
```

## Hash Tables

### ActionScript 3

```ActionScript
var table:Object = new Object ();
table["key"] = 100;
 
trace (table.hasOwnProperty ("key"));
 
for (var key:Object in table) {
 
   trace (key + " = " + table[key]);
 
}
 
delete table["key"];
```

### Haxe

```haxe
var table = new Map<String,Int> ();
table.set ("key", 100);
 
trace (table.exists ("key"));
 
for (key in table.keys ()) {
 
   trace (key + " = " + table.get (key));
 
}
 
table.remove ("key");
```

## Rest Parameters

### ActionScript 3

```ActionScript
function test (...params):void {
 
}
 
test (1, 2, 3);
```

### Haxe

```haxe
function test (params:Array<Dynamic>) {
 
}
 
Reflect.makeVarArgs (test) (1, 2, 3);
```

## Reflection

### ActionScript 3

```ActionScript
var foo = object["foo"];
 
bar.apply (this, [ "hi" ]);
```

### Haxe

```haxe
var foo = Reflect.field (object, "foo");
 
Reflect.callMethod (this, bar, [ "hi" ]);
```

## Constants

### ActionScript 3

```ActionScript
private const gravity:Number = 9.8;
```

### Haxe

```haxe
private inline static var gravity = 9.8;
```

## Function Types

### ActionScript 3

```ActionScript
function hello (msg:String):void {
 
}
 
var type:Function = hello;
```

### Haxe

```haxe
function hello (msg:String):Void {
 
}
 
var type:String->Void = hello;
 
// can also use Dynamic
```

## Getters and Setters

### ActionScript 3

```ActionScript
function get x ():Number {
 
   return _x;
 
}
 
function set x (value:Number):void {
 
   _x = value;
 
}
```

### Haxe

```haxe
public var x (get, set):Float;
 
function get_x ():Float {
 
   return _x;
 
}
 
function set_x (value:Float):Float {
 
   return _x = value;
 
}
```

## Read-Only Properties

### ActionScript 3

```ActionScript
function get x ():Float {
 
   return _x;
 
}
```

### Haxe

```haxe
public var x (default, null):Float;
 
// null allows private access
// `never` would restrict all access
```

## Missing Features

Haxe does not currently support custom namespaces, and methods do not provide an arguments property.

## Additional Features

In addition to most of the features of Actionscript 3, Haxe includes support for [enums](http://haxe.org/ref/enums), type parameters (generics), structures, typedefs, custom iterators, conditional compilation, inlining and more.