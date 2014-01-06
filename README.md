SurfStack Standards for PHP Readme
==================================

The coding standards are based off the Allman indent style. The style puts the
brace associated with a control statement on the next line, indented to the
same level as the control statement. Statements within the braces are indented
to the next level.

The SurfStack Standards are designed to enable creation of easy to read code.

Example:

```php
<?php
while (x == y)
{
    foo();
}

if (x == y) 
{
    x++;
    foo();
} 
else 
{
    x--;
    bar();
}
?>
```

Information
-----------

There are no "correct" standards. They are simply designed to keep shared code
similar and clean.

The topics include:
- [Indenting and Line Length](standards.md#indenting-and-line-length)
- [Naming Conventions](standards.md#naming-conventions)
- [Class Variables and Methods](standards.md#class-variables-and-methods)
- [Constants](standards.md#constants)
- [File Formats](standards.md#file-formats)
- [E_STRICT Compatible](standards.md#e_strict-compatible)
- [Control Structures](standards.md#control-structures)
- [Ternary Operators](standards.md#ternary-operators)
- [Function Calls](#function-calls)
- [Class Definitions](standards.md#class-definitions)
- [Function Definitions](standards.md#function-definitions)
- [Arrays](standards.md#arrays)
- [Comments](standards.md#comments)
- [Including Code](standards.md#including-code)
- [PHP Code Tags](standards.md#php-code-tags)
- [Example URLs](standards.md#example-urls)
- [Error Handling](standards.md#error-handling)
- [Best Practices](standards.md#best-practices)

Sources
-------

The [PEAR Coding Standards](http://pear.php.net/manual/en/standards.php)
was used as a base template.