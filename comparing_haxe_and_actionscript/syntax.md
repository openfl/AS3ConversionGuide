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



## Whitespace

## Comments

## Literals

## Keywords