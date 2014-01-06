SurfStack Standards for PHP Readme
==================================

The coding standards are based off the Allman indent style. The style puts the
brace associated with a control statement on the next line, indented to the
same level as the control statement. Statements within the braces are indented
to the next level.

The SurfStack Standards are designed to enable creation of easy to read code.

Example:

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

Disclaimer
----------

There are no "correct" standards. They are simply designed to keep shared code
similar and clean.

Sources
-------

Much of the information is pulled from the [http://pear.php.net/manual/en/standards.php]PEAR Coding Standards