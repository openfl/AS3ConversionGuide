# Operators

## Arithmetic Operators

ActionScript and Haxe both use the following operators, and behave similarly:

|    |    |    |
|----|----|----|
| `+` | `-` | `*` |
| `/` | `%` | `++` |
| `--` |

## Equality and Comparison Operators

ActionScript and Haxe both use the following operators, and behave similarly:

|    |    |    |
|----|----|----|
| `==` | `!=` | `<` |
| `>` | `<=` | `>=` |

However, ActionScript has two additional operators which are not used in Haxe:

 * `===`
    
    In ActionScript 3.0, an equality (`==`) comparison can sometimes make a conversion. For example, the following is `true` in ActionScript:
    
    ```ActionScript
    var a:String = "5";
    var b:Number = 5;
    trace (a == b);
    ```
    
    The same code in a compile error in Haxe. Haxe handles the ordinary equality (`==`) operator in strict way.
    
 * `!==`
    
    Similar to the strict equality (`===`) operator, the strict inequality (`!===`) operator is not valid Haxe syntax. Haxe does not automatically convert types in a conversion like ActionScript 3.0.

## Logical Operators

ActionScript 3.0 and Haxe share the following logical operators:

|    |    |    |
|----|----|----|
| `!` | `&&` | `||` |

Haxe does not support logical assignment operators.

 * `&&=`
    
    Haxe does not support logical AND assignment (`&&=`) in a single operator, but this can easily be replaced by expanding the expression:

    _Before_
    
    ```ActionScript
    mask &&= BIT_VALUE;
    ```
    
    _After_
    
    ```haxe
    mask = mask && BIT_VALUE;
    ```
    
 * `||=`
    
    Haxe does not support logical OR assignment (`||=`) in a single operator, but this can easily be replaced by expanding the expression:
    
     _Before_

    ```ActionScript
    mask ||= BIT_VALUE;
    ```
    
    _After_
    
    ```haxe
    mask = mask || BIT_VALUE;
    ```
    
## Bitwise Logical Operators

ActionScript 3.0 and Haxe share the following operators, and behave similarly:

|    |    |    |
|----|----|----|
| `~` | `&` | `|` |
| `^` | `&=` | `|=` |
| `^=` |

## Bitwise Shift Operators

ActionScript 3.0 and Haxe share the following operators, and behave similarly:

|    |    |    |
|----|----|----|
| `<<` | `>>` | `>>>` |
| `<<=` | `>>=` | `>>>=` |

## Other Operators


