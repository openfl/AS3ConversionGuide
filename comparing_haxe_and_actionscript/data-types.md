# Data Types

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
