SurfStack Standards for PHP
===========================

The coding standards are based off the Allman indent style. The style puts the
brace associated with a control statement on the next line, indented to the
same level as the control statement. Statements within the braces are indented
to the next level.

Indenting and Line Length
-------------------------

- Use an indent of 4 spaces with no tabs. This helps to avoid problems with
diffs, patches, SVN history and annotations.
- Lines should not be longer than 80 characters

Naming Conventions
------------------

- Global functions should be named using the "studly caps" style (also referred
to as "bumpy case" or "camel caps").
- In addition, they should have the package name as a prefix, to avoid name
collisions between packages.

```php
<?php
XML_RPC_serializeData();

SurfStack_isAdmin();
?>
```

- Classes should be given descriptive names.
- Avoid using abbreviations where possible.
- Class names should always begin with an uppercase letter.
- Separate words with underscores.

```php
<?php
class Log
{
    foo();
}

class Net_Finger
{
    foo();
}
 
class HTML_Upload_Error
{
    foo();
}
?>
```

Class Variables and Methods
---------------------------

 - Should be named using the "studly caps" style (also referred to as "bumpy case" or "camel caps").
 - Underscores should not be used.
 - Property names SHOULD NOT be prefixed with a single underscore to indicate protected or private visibility.

```php
<?php
$counter = true;

connect();

getData();

buildSomeWidget();
?>
```

Constants
---------

- Constants should always be all-uppercase, with underscores to separate words.
- Prefix constant names with the uppercased name of the class/package they are
used in.
- The true, false and null constants are excepted from the all-uppercase rule,
and must always be lowercase.

```php
<?php
define('DB_DATASOURCENAME', true);

define('SERVICES_AMAZON_S3_LICENSEKEY', false);
?>
```

File Formats
------------

- There SHOULD NOT be any line feeds after the closing PHP tag (?>).
- All scripts should be stored as ASCII text.
- Use ISO-8859-1 or UTF-8 character encoding.
- The encoding may be declared at the top of the file.

```php
<?php
declare(encoding = 'utf-8');
?>
```

E_STRICT Compatible
-------------------

- All the code must not produce any warnings or errors when PHP's error
reporting level is set to E_ALL | E_STRICT.

```php
<?php
// Report all PHP errors in PHP 5.4.0 and newer
error_reporting(E_ALL);

// Same as error_reporting(E_ALL)
ini_set('error_reporting', E_ALL);
?>
```

Control Structures
------------------

- There should be one space between the control keyword and opening parenthesis to distinguish them from function calls.
- Use curly braces even in situations when there is one line of code. Having them increases readability and decreases the likelihood of logic errors being introduced when new lines are added.
- These include if, for, while, switch, etc.

```php
<?php
if (($x == $y) || ($x == $z))
{
    foo();
}
elseif (($x != $y) && ($x != $z))
{
    bar();
}
else
{
    foobar();
}

switch ($x)
{
    case 1:
        foo();
        break;
    
    case 2:
        bar();
        break;
    
    default:
        foobar()
        break;
}
?>
```

- Conditions can be split onto several lines.

```php
<?php
if (($x == $y
    || $x == $z)
    && $x != 5
    && $z != 10
)
{
    foo();
}
?>
```

Ternary Operators
-----------------

- Surround the statement in parenthesis.
- Ensure there is a space on both sides of the question mark (?) and colon (:).

```php
<?php
$x = ($y == '' ? true : false);
?>
```

- Separate out each condition to a separate line if it is too long.

```php
<?php
$x = ($y == ''
    ? callAReallyLongFunctionName()
    : callADifferentReallyLongCuntionName
);
?>
```

Function Calls
--------------

- Functions should be called with no spaces between the function name, the
opening parenthesis, and the first parameter; spaces between commas and each
parameter, and no space between the last parameter, the closing parenthesis, and the semicolon.

```php
<?php
$foo = bar($x, $y, $z);
?>
```

- In the case of a block of related assignments, more space may be inserted to
promote readability.

```php
<?php
$short         = foo($x);
$long_variable = foo($y);
?>
```

- To support readability, parameters in subsequent calls to the same
function/method may be aligned by parameter name.

```php
<?php
$foo('param1',     'second',        true);
$foo('parameter2', 'third',         false);
$foo('param3',     'verrrrrrylong', true);
?>
```

- Parameters can be split onto several lines.

```php
<?php
$this->foo->bar->callThisFunctionWithALongName(
    $parameterOne,
    $parameterTwo,
    $aVeryLongParameterThree
);
?>
```

Class Definitions
-----------------

- Class declarations have their opening brace on a new line.

```php
<?php
class Foo_Bar
{
    foo();
}
?>
```

Function Definitions
--------------------

- Function declarations follow the "Allman style".

```php
<?php
function foo($arg1, $arg2 = '')
{
    bar();
}
?>
```

- Functions with many parameters may need to be split onto several lines.

```php
?php
function someFunctionWithAVeryLongName($firstParameter = 'something',
    $secondParameter = 'booooo',
    $third = null,
    $fourthParameter = false,
    $fifthParameter = 123.12,
    $sixthParam = true
)
{
    foobar();
}
?>
```

Arrays
------

- Assignments in arrays should be aligned on several lines.
- All values should have trailing commas to keep code diffs minimal.

```php
<?php
$arrBar = array(
    'foo',
    'bar',
);

$arrFoo = array(
    'foo'  => 'bar',
    'spam' => 'ham',
);

$arrFooBar = array(
    'foo' => array(
        'x' => 5,
        'y' => 10,
    ),
    'bar' => array(
        'spam' => 'ham',
    ),
);
?>
```

Comments
--------

- C style comments (/* */) and standard C++ comments (//) are recommended.
- Use of Perl/shell style comments (#) is discouraged.
- Non-documentation comments are strongly encouraged. A general rule of thumb
is that if you look at a section of code and think "Wow, I don't want to try
and describe that", you need to comment it before you forget how it works.
- Complete inline documentation comment blocks (docblocks) must be provided.

Including Code
--------------

- Anywhere you are unconditionally including a class file, use require_once.
- Anywhere you are conditionally including a class file (for example, factory
methods), use include_once.

PHP Code Tags
-------------

- Always use <?php ?> to delimit PHP code, not the <? ?> shorthand. This is
required for PEAR compliance and is also the most portable way to include PHP
code on differing operating systems and setups.

Example URLs
------------

- Use example.com, example.org and example.net for all example URLs and email
addresses per [http://www.faqs.org/rfcs/rfc2606.html]RFC 2606.

Error Handling
--------------

- An error is defined as an unexpected, invalid program state from which it is
impossible to recover.
- When an error occurs, throw new new Exception() or ErrorException()

```php
<?php
// Throw regular exception
throw new \Exception();

// Throw exception with detailed information
throw new \ErrorException($e->getMessage(),
    $e->getCode(),
    0,
    $e->getFile(),
    $e->getLine()
);
?>
```

Best Practices
--------------

- Use single quotes instead of double quotes in strings. If the string is
enclosed in double-quotes ("), PHP will interpret more escape sequences for
special characters which is slower when not needed.
- Use double quotes for string that contain many single quotes like MySQL
queries.

```php
<?php
$foo = 'This is faster';
$bar = "This is slower";

$foobar = "SELECT * FROM users WHERE first_name='Sam'";
?>
```

- Return at the beginning of a function if possible

```php
<?php
// This is good
function foo($bar, $baz)
{
    if (!$foo)
    {
        return null;
    }

    //assume
    //that
    //here
    //is
    //the
    //whole
    //logic
    //of
    //this
    //method
    return $calculated_value;
}

// This is bad
function foo($bar, $baz)
{
    if ($foo)
    {
        //assume
        //that
        //here
        //is
        //the
        //whole
        //logic
        //of
        //this
        //method
        return $calculated_value;
    }
    else
    {
        return null;
    }
}
?>
```