# Type declarations

https://www.php.net/manual/en/language.types.declarations.php

### strict_types

```php
<?php
declare(strict_types=1);
```

[declare](https://www.php.net/manual/en/control-structures.declare.php)

The declare construct is used to set execution directives for a block of code. The syntax of declare is similar to the syntax of other flow control constructs:

 declare (directive)\
    statement

The directive section allows the behavior of the declare block to be set.

Currently only three directives are recognized:
- the **ticks** directive
- the **encoding** directive
- the **strict_types** directive

[strict_types](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.strict)

By default, PHP will coerce values of the wrong type into the expected scalar type declaration if possible.\
For example, a function that is given an int for a parameter that expects a string will get a variable of type string.

example:
```php
<?php
declare(strict_types=1);

function sum(int $a, int $b) {
    return $a + $b;
}

var_dump(sum(1, 2));
var_dump(sum(1.5, 2.5));
?>
```

output:
```
int(3)

Fatal error: Uncaught TypeError: sum(): Argument #1 ($a) must be of type int, float given, called in - on line 9 and defined in -:4
Stack trace:
#0 -(9): sum(1.5, 2.5)
#1 {main}
  thrown in - on line 4
```
