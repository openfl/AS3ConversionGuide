# Variables

ActionScript and Haxe both use the `var` keyword to define a new variable. This can store a reference to an object, or it can store a value, such as an integer or string.

## Naming Limitations

A class level variable, or _property_, must have a unique name.

```haxe
class Test {
    
    public var hello:String;
    public var hello:Int; // error, cannot reuse name
    
    public function new () {
        
    }
    
}
```

In ActionScript 3.0, you cannot use a name more than once in a local variable either, but in Haxe, you _are_ allowed to redefine a local variable.

```haxe
public function hello ():String {
    
    var value = "Hello";
    trace (value);
    
    var value = 100; // not allowed in ActionScript
    trace (value);
    
}
```

Variable names cannot be a reserved keyword, and cannot use special characters (except for "_"). ActionScript 3.0 allows use of the dollar sign ("$") character in variable names, but their use is not allowed in Haxe.

## Naming Conventions

ActionScript and Haxe commonly use "camel case" when naming variables. This means that the name starts in lowercase, but uses uppercase at the start of each new word (such as `itemCount` or `applesAndBananas`).

Both languages also commonly use an underscore ("_") at the beginning of a private variable name (such as `_secretValue`).

It is also recommended to try and use variable names that are descriptive. This can be difficult to do, but will always make it easier to understand code without additional comments. `FORCE_OF_GRAVITY`, for example, will probably be easier to understand than `_g` in most cases.

It is also common convention to use all capital letters for a constant value, such as `SPEED_OF_LIGHT`.

## Access Control

ActionScript 3.0 supports four built-in levels of access for class properties:

 * `public`

    The variable will be accessible to other classes
    
 * `private`
    
    The variable will be accessible only within the current class
    
 * `protected`
    
    The variable will be accessible within the current class, or by classes that extend the current class
    
 * `internal`
    
    The variable will be accessible within the current class, and other classes in the same package
    
Haxe simplifies these controls to two levels of access. `public` behaves similarly to the ActionScript `public` level of access, and `private` behaves similarly to the Actionscript `protected` level of access.

You can use `@:access`, `@:allow` or `@:privateAccess` meta-data in Haxe to access or allow private access between classes, supporting other use cases.

Haxe also adds support for controlling read and write access to a variable, using the following syntax:

```haxe
public var hello (read, write):String;
```

For example,

```haxe
public var hello (default, null):String;
```

The following kinds of read and write access are supported:

 * `default`
    
    Access will perform as it would normally
    
 * `get`
    
    Read access will use a getter function, named `get_hello` (or whatever the property name is), when reading the value
    
 * `set`
    
    Write access will use a setter function, named `set_hello` (or whatever the property name is), when writing the value
    
 * `null`
    
    Read or write access will be allowed inside of the current class, or children of the current class, but will not be allowed externally
    
 * `never`
    
    Read or write access will never be allowed, even inside the current class

## Getters and Setters

ActionScript 3.0 allows support for simulating read-only variables, or variables with a custom setter, by using a `get` or a `set` function, and an additional private variable.

```ActionScript
private var _readOnly:String;

public get function readOnly ():String {
    
    return _readOnly;
    
}
```

Haxe supports more powerful access control per-variable, so this is not required. However, both languages support get and set functions when more powerful control is required:

*ActionScript 3.0*

```ActionScript
private var _custom:String;

public get function custom ():String {
    
    return _custom;
    
}

public set function custom (value:String):void {
    
    _custom = value;
    
}
```

*Haxe*

```haxe
public var custom (get, set):String;

private var _custom:String;

private function get_custom ():String {
    
    return _custom;
    
}

private function set_custom (value:String):String {
    
    return _custom = value;
    
}
```

## Constants

Constants are properties that have a fixed value, and do not ever change. ActionScript 3.0 defines a `const` keyword when declaring a constant property, while Haxe uses the `inline` keyword instead.

```haxe
public static inline var FORCE_OF_GRAVITY = 9.8;
```
