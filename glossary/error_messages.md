# Error Messages

## Class not found: Object

The `Object` type in Haxe is called `Dynamic`. It is equivalent to the `*` type in ActionScript. It is also possible to remove some type declarations since Haxe supports type inference, like `var foo = {};`

## Class not found: Function

The `Function` type in Haxe can be described either by using `Dynamic`, or by using the signature of the method. For example, if the method accepts no parameters and returns a string, you could describe the function as `Void -> String`. If it accepted a boolean and a string, but had no return value, you could use `Bool -> String -> Void` as the type.

It is also possible to remove some type declarations since Haxe supports type inference, like `var foo = function () {};`

## Class not found: Number

The `Number` type in Haxe is called `Float`. It is also possible to remove some type declarations since Haxe supports type inference, like `var foo = 0.0;`

## Class not found: Boolean

The `Boolean type` in Haxe is called `Bool`. It is also possible to remove some type declarations since Haxe supports type inference, like `var foo = false;`

## Class not found: RegExp

You can try using the Haxe regular expression class, `EReg`

## Invalid number of type parameters for Array

The `Array` type in Haxe expects type parameters, to describe what the array contains. You can create a generic array using `Array<Dynamic>`, or you can be more specific by using the appropriate types, like `Array<Int>` or `Array<Array<String>>`.

It is also possible to remove some type declarations since Haxe supports type inference, like `var foo = [ 1, 2 ];`

## Missing ;

Haxe does not automatically close declarations based on new lines. For example, `var foo = 1;` needs to end with a semicolon, otherwise you will receive this error.

This can also be an indication that something else is wrong:

 * You may need to replace `package { ... }` with `package;`
 * You may need to fix a bad type on the line before, like `uint`
 * You may need to remove a bad keyword, like `delete`
 * You may need to change a value that uses a restricted Haxe keyword, like `cast` or `callback`
 * You may need to replace an `as` keyword with `cast`, `cast ()` or `Std.as()`

## Unexpected }

There may be a logical error before this point in your code, or you have a mismatch in your curly braces. For example, if you change `package {` to `package;`, you may have forgotten to remove the closing brace lower in the file.

## Unexpected final

Unlike ActionScript, Haxe does not have a `final` keyword. You can either remove the keyword or use `@:final` instead. If you use the `@:final` meta-tag, however, make sure that it appears before other keywords, like `@:final public function`, not `public @:final function`

## Unexpected foo (or other variable name)

This may be caused by a declaration which is not compatible with Haxe, like `typeof foo`, or you may need to convert a Flash getter or setter.

If a getter or setter is being used to limit access to a variable, like setting it to read-only, you can do this when defining a variable in Haxe, like `var foo (default, null):String`

Otherwise, you can use the same syntax to use a getter or a setter, like `var foo (get, set):String`, then define your getter and setter methods later in the class (using the prefix "get_" or "set", respectively).

## Unexpected $foo (or other variable name)

Haxe does not allow the dollar sign in variable or method names.

## Unexpected =

This might indicate that there is a bad type before the equal sign, like “uint”, or this may be caused by some kinds of compact syntax that are not compatible with Haxe.

For example, if the original code had `foo ||= bar`, you can replace it with `if (foo == null) foo = bar;`

## Unexpected public

You may need to replace `public class` with `class`

## Type name should start with an uppercase letter

By convention, types like classes, interfaces, typedefs and enums begin with an uppercase letter.

This may also occur if you attempt to use a namespace, which is not supported in Haxe, or it may occur when referencing a global method that does not exist in Haxe. For example, `getTimer` should be `Lib.getTimer`, or methods like `getDefinitionByName` should be replaced with calls to the `Type` or `Reflect` classes.

## Unexpected /

This may occur when there is a regular expression that needs to be replaced.

## Unexpected var

This can occur if a `for` loop is not formatted for Haxe.

In other languages, a loop like `for (var i:uint = 0; i < 100; i++)` is fairly common. Written for Haxe, the same loop would be `for (i in 0…100)`

Similarly, a loop like `for each (var i:String in myArray)` in ActionScript would be `for (i in myArray)` when written for Haxe.

## Unexpected internal

Haxe does not have an `internal` namespace. You should change it to `private`, then use the `@:access`, `@:allow` or (for a single-line call) `@:privateAccess` meta-data to access or allow private members.

## Unexpected ...

Haxe does not support "rest" parameters like ActionScript 3.

There are ways to recreate the same functionality using `Reflect.makeVarArgs`, but it probably is best to refactor so that the number of parameters is known.

## Unexpected <end of file>

This might occur if you are missing a closing curly bracket in your code.

## Unexpected dynamic

In ActionScript, the `dynamic` keyword means that a class can have new variables or methods assigned to it as a dynamic object. This is possible in Haxe by implementing `Dynamic` as an interface.

For example, `dynamic class Foo implements Bar` can be replaced with `class Foo implements Bar implements Dynamic`

## Unexpected implements

This probably means that a comma is missing.

For example, replace `extends Foo implements Bar` with `extends Foo implements Bar`

## Unexpected {

This might mean that you forgot a parenthesis in your code.

## Unexpected is

You can replace “Foo is Bar” with “Std.is (Foo, Bar)”

## Unexpected as

There is more than one way to perform casting in Haxe. In order to perform an unsafe (but fast) cast between types, you can use the “cast” keyword with parenthesis, like “cast foo”.

In order to perform a safe cast, use parenthesis, like “cast (foo, Bar)”. This is similar to using Std.as in order to perform casting.

You can use Std.int, Std.parseFloat, Std.parseInt and Std.string in order to convert between basic types.

## Unexpected protected

The Haxe language does not have a “protected” keyword, but the “private” scope acts like “protected” in other languages.

## Unexpected *

This may mean that you need Dynamic in place of * for a type, or it may be caused by a wild card import, which is not supported in Haxe.

A statement like “import flash.display.*;” can be replaced with “import flash.display.Sprite;”
