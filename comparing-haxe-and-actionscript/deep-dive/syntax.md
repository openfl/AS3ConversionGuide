# Syntax

## Case Sensitivity

ActionScript 3.0 and Haxe are both case-sensitive languages, so both of the following are different variables:

```haxe
var hello:String;
var Hello:String;
```

## Semicolons

ActionScript 3.0 and Haxe both use semicolons (`;`) to terminate a statement. Good coding standards in ActionScript encourage the use of semicolons, but they are optional.

In Haxe, the use of semicolons is not optional.

```haxe
var hello:String; // correct
var hello:String // incorrect
```

## Parentheses

In ActionScript 3.0, parentheses (`()`) can be used in three ways, but only two of these are valid in Haxe.

You can use parentheses to group operations:

```haxe
trace (1 + (2 * 3)); // 7
trace ((1 + 2) * 3); // 9
```

You can also use parentheses to pass one or more parameters to functions or methods:

```haxe
trace ("hello");
```

ActionScript also supports the use of commas to separate multiple expressions and return the result of the final expression. For example:

```ActionScript
var a:int = 1;
var b:int = 2;
trace ((a++, b++, a + b)); // 5
```

The above syntax can be confusing, and is not supported in Haxe. The same code can be handled by expanding the expression:

```haxe
var a = 1;
var b = 2;
a++;
b++;
trace (a + b);
```

...or using a function:

```haxe
var a = 1;
var b = 2;
trace (function () { a++; b++; return a + b; } ());
```

## Code Blocks

Code encased by curly braces (`{}`) are called a code block. The body of many portions of ActionScript and Haxe are grouped together using code blocks.

```haxe
public function hello ():String {
    
    return "World";
    
}
```
```haxe
if (raining) {
    
    useUmbrella ();
    
}
```

## Whitespace

Spaces, tabs and line breaks are referred to as whitespace. Actionscript and Haxe both allow whitespace to make code easier to read.

```haxe
class Test {
    
    public function new () {
        
    }
    
}

class Test2 { public function new() {} }
```

## Comments

Actionscript and Haxe both allow for single-line or multi-line comments. A comment will not be compiled, allowing the addition of helpful notes or as a method of quickly disabling code.

```haxe
// This is a single line comment

/* This is
   a multi-line
   comment */
```

## Literals

A literal is a fixed value in your code, Haxe and ActionScript are similar in the types of literals you can use:

```haxe
100
-2.1
"hello"
null
true
false
```

ActionScript has an `undefined` literal which is not used in Haxe. The following returns `undefined` in `ActionScript`, but is a compile error in Haxe:

```haxe
object = { a: "b", c: "d" };
trace (object.e);
```

Instead, use the Haxe `Reflect` class to check if a field exists, or use static types.

```haxe
if (Reflect.hasField (object, "e")) {
    
    trace (Reflect.field (object, "e"));
    
}
```

## Square Brackets

In ActionScript and Haxe, square brackets (`[]`) can be used to define an array literal:

```haxe
var colors = [ "red", "blue", "green" ];
```

Square brackets can also be used to access array values:

```haxe
var firstColor = colors[0];
```

Haxe allows support for array access on user-created abstract objects, in addition to core types.

ActionScript also allows the use of square brackets to access fields using a string-based name, but this is not supported in Haxe. Use the `Reflect` class in Haxe in order to reference a field dynamically.

_ActionScript 3.0_

```ActionScript
clip.x = 100;
clip["y"] = 100;
```

_Haxe_

```haxe
clip.x = 100;
Reflect.setField (clip, "y", 100);
```

## Angle Brackets

ActionScript 3.0 uses angle brackets (`<>`) for the `Vector.<>`. Haxe provides support for _type parameters_ in the `Array<>`, `Map<>` and multiple other types in the language, and allows use of type parameters in user classes as well.

When describing the type of an `Array`, ActionScript will always treat the array as if it is dynamic. In Haxe, arrays are typed based on their contents, which improves performance and can eliminate confusing errors:

```haxe
var values:Array<Int> = [ 0, 1, 2, 5 ];
var names:Array<String> = [ "Doug", "Richard", "Harrison" ];
```

## Arrow Tokens

Haxe supports a special arrow token (`->`) syntax, which is used when describing a function. The ActionScript does not allow for different types based on the signature of a function. Instead, every function in ActionScript is described as type `Function`. Haxe allows for `Dynamic` to describe any function, but uses "arrow tokens" when a function signature is described specifically. For example, a function that accepts a `Bool` and returns an `Int` would be described as `Bool->Int`, and a function that accepts two boolean arguments instead would be `Bool->Bool->Int`

```haxe
private function onMouseDown (x:Float, y:Float):Void {
    
}
```
```haxe
var handler:Float->Float->Void = onMouseDown;
handler (100, 100);
```

## Keywords

ActionScript and Haxe share many reserved words and keywords:

|    |    |    |
|----|----|----|
| `break` | `case` | `catch` |
| `class` | `continue` | `default` |
| `do` | `dynamic` | `else` |
| `extends` | `false` | `for` |
| `function` | `if` | `implements` |
| `import` | `in` | `interface` |
| `new` | `null` | `override` |
| `package` | `private` | `public` |
| `return` | `static` | `super` |
| `switch` | `this` | `throw` |
| `true` | `try` | `var` |
| `while` |

The Haxe programming language is designed to limit the number of keywords, so there are a number of keywords which are in ActionScript 3.0 that are not keywords in Haxe:

 * `as`

    In ActionScript 3.0, `as` is used for casting. Adobe references `cast` as a "future" keyword that has not been implemented in the language.

    ```ActionScript
    var clip:MovieClip = event.currentTarget as MovieClip;
    ```
    
    Haxe uses `cast` when casting between types, in order to perform a safe cast (which is slower, but throws an error if it is not possible), use parentheses:
    
    ```haxe
    var clip = cast (event.currentTarget, MovieClip);
    ```

    ...otherwise, an unsafe cast occurs without parentheses and a second argument.
    
     ```haxe
    var clip:MovieClip = cast event.currentTarget;
     ``` 

 * `const`
    
    Actionscript uses the `const` keyword to define a constant value. Because Haxe supports inlining, a `const` keyword is not necessary.
    
    ```haxe
    public static inline var gravity = 9.8;
    ```
    
 * `each`
    
    ActionScript has separate "for in" or "for each in" loops, but in Haxe these are simplified to a single "for in" loop.
    
    ```haxe
    var fruits = [ "apple", "pear", "orange" ];

    for (fruit in fruits) {
        
        trace (value);
        
    }
    ```
    
    If you need to iterate over the names of the fields in an object, use `Reflect.fields`:
    
    ```haxe
    var object = { a: "b", c: "d" };
    
    for (field in Reflect.fields (object)) {
        
        trace (field); // returns "a" then "c"
        
    }
    ```haxe
    
 * `final`
    
    ActionScript uses the `final` keyword to specify a class that cannot be extended. Haxe supports the same, but it uses a `@:final` meta-data tag instead:
    
    ```haxe
    @:final class Test {
        
    }
    ```
    
 * `finally`
    
    Haxe does not support `try/catch/finally` so cleanup logic must occur inside a `catch`, or after the `try/catch` statement.

 * `include`
    
    Haxe does not support an `include` keyword, there are methods of replicating the same behavior using a custom macro, but in general, it is recommended that classes, typedefs, `using` and other techniques are implemented to share code within a project.
    
 * `instanceof`
    
    The ActionScript 3.0 keyword, `instanceof`, can be replaced with `Std.is`
    
    ```haxe
    trace (Std.is (sprite, DisplayObject));
    trace (Std.is ("hello", String));
    trace (Std.is (5, Int));
    ```
    
 * `internal`
    
    Haxe has support for both `public` and `private` keywords, which are simpler to understand, and cover the majority of use cases.
    
    Haxe supports three meta-data tags (`@:allow`, `@:access` and `@:privateAccess`) which each provide different methods of accessing a `private` member. This can provide the same function as `internal`, or like "friend classes" in other languages.
    
    ```haxe
    class Secret {
        
        private var password:String;
        
    }
    ```
    ```haxe
    @:access(Secret)
    class Login {
        
        public function new () {
            
            var password = Secret.password;
            
        }
        
    }
    ```
    
 * `namespace`
    
    Haxe does not support custom namespaces like ActionScript 3.0.
    
 * `native`
    
    ActionScript has a `native` keyword when a method is a wrapper around a native method. Haxe has `extern` classes for working with native APIs, and depending on the platform, "CFFI" or "JNI" for accessing methods or properties between different runtime environments.
    
    On HTML5, it is possible to also implement `untyped` JavaScript code directly.
    
    ```haxe
    untyped __js__ ("window.alert ('Hello!')");
    ```
    
    ...extern classes tend to help provide a nicer API, however:
    
    ```haxe
    Browser.alert ("Hello!");
    ```
    
 * `protected`
    
    The `private` keyword in Haxe behaves similar to the `protected` keyword in ActionScript.
    
 * `typeof`
    
    ActionScript 3.0 uses the `typeof` keyword to return a generic String value for the current object:
    
    ```ActionScript
    switch (typeof obj) {
        case "boolean": trace ("obj is a boolean"); break;
        case "number": trace ("obj is a number"); break;
        default:
    }
    ```
    
    Haxe allows a similar check using `Type.typeof`, though it returns a static type (not a String).
    
    ```haxe
    switch (Type.typeof (obj)) {
        case TBool: trace ("obj is a boolean");
        case TInt, TFloat: trace ("obj is a number");
        default:
    }
    ```
    
 * `use`
    
    Haxe does not support custom namespaces like ActionScript 3.0.
    
 * `void`
    
    Haxe uses `Void` instead of `void` (for better consistency with other type names).
    
 * `with`
    
    The ActionScript 3.0 `with` keyword is a shorthand approach that can reduce the amount of code that is written, but it has some limitations (such as not being able to declare new variables inside) which can make it unpredictable to use.
    
    ```ActionScript
    var clip = new MovieClip ();
    with (clip) {
        x = 100;
        y = 100;
    }
    ```
    
    Haxe does not support the `with` keyword, it may make code more verbose, but it can make code simpler to understand and more reliable.
    
    ```haxe
    var clip = new MovieClip ();
    clip.x = 100;
    clip.y = 100;
    ```
    
Haxe also has additional keywords that are not defined in ActionScript:

|    |    |    |
|----|----|----|
| `cast` | `enum` | `extern` |
| `inline` | `never` | `typedef` |
| `untyped` | `using` | 
