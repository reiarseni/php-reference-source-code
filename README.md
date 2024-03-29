
# PHP 8.0 Reference

+ [PHP 8.0](https://www.php.net/releases/8.0/es.php)
+ [PHP 8.1](https://www.php.net/releases/8.1/es.php)
+ [PHP 8.2](https://www.php.net/releases/8.2/es.php) 
+ [PHP 8.3](https://www.php.net/releases/8.3/es.php)

# Quick PHP reference using only source code examples. 

# Chapter 01 - Using PHP

```html
<!doctype html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>PHP Test</title>
  </head>
  <body>
    <?php echo "Hello World"; ?>
  </body>
</html>
```

### Comments
```php
<?php 
  // single-line comment
  #  single-line comment
  /* multi-line 
     comment */
?>
```

# Chapter 02 - Variables

```php 
$myVar;
$myVar = 10;
echo $myVar; // "10"

$myVar = 1;   // int type
$myVar = 1.5; // float type

// Float type evaluated as string type 
echo $myVar; // "1.5"

$myInt = 1234; // decimal number
$myInt = 0b10; // binary number (2 decimal)
$myInt = 0123; // octal number (83 decimal)
$myInt = 0x1A; // hexadecimal number (26 decimal)

$myFloat = 1.234;
$myFloat = 3e2; // 3*10^2 = 300

$myBool = true;
$myNull = null; // variable is set to null

$myInt = $myNull + 0;      // numeric context (0)
$myBool = $myNull == true; // bool context (false)
echo $myNull;              // string context ("")
echo $myUndefined;         // error (as of PHP 8)
```

# Chapter 03 - Operators

### Arithmetic operators

```php
$x = 4 + 2; // 6 // addition
$x = 4 - 2; // 2 // subtraction
$x = 4 * 2; // 8 // multiplication
$x = 4 / 2; // 2 // division
$x = 4 % 2; // 0 // modulus (division remainder)
$x = 4 ** 2; // 16 // exponentiation
```

### Combined assignment operators
```php
$x = 1;
$x += 5; // $x = $x+5;
$x -= 5; // $x = $x-5;
$x *= 5; // $x = $x*5; 
$x /= 5; // $x = $x/5;
$x %= 5; // $x = $x%5;
$x **= 5; // $x = $x**5;
```

### Increment and decrement operators
```php
$x++; // $x += 1;
$x--; // $x -= 1;

$x++; // post-increment
$x--; // post-decrement
++$x; // pre-increment
--$x; // pre-decrement

$x = 5; $y = $x++; // $x=6, $y=5
$x = 5; $y = ++$x; // $x=6, $y=6
```

### Comparison operators
```php
$x = (2 == 3);  // equal to (false)
$x = (2 != 3);  // not equal to (true)
$x = (2 <> 3);  // not equal to (alternative)
$x = (2 === 3); // identical (false) 
$x = (2 !== 3); // not identical (true)
$x = (2 > 3);   // false,greater than (false)
$x = (2 < 3);   // less than (true)
$x = (2 >= 3);  // greater than or equal to (false)
$x = (2 <= 3);  // less than or equal to (true)

$x = (1 ==  "1"); // true (same value)
$x = (1 === "1"); // false (different types)

$x = 1 <=> 1; // 0 (1 == 1)
$x = 3 <=> 2; // 1 (3 > 2)
$x = 1 <=> 2; // -1 (1 < 2)
```

### Logical operators
```php
$x = (true && false); // logical and (false)
$x = (true || false); // logical or (true)
$x = !true;           // logical not (false)
```
### Bitwise operators
```php
$x = 5 & 4;  // 101 & 100 = 100 (4) // and
$x = 5 | 4;  // 101 | 100 = 101 (5) // or
$x = 5 ^ 4;  // 101 ^ 100 = 001 (1) // xor (exclusive or)
$x = 4 << 1; // 100 << 1  =1000 (8) // left shift
$x = 4 >> 1; // 100 >> 1  =  10 (2) // right shift
$x = ~4;     // ~00000100 = 11111011 (-5) // invert

$x=5; $x &= 4;  // 101 & 100 = 100 (4) // and
$x=5; $x |= 4;  // 101 | 100 = 101 (5) // or
$x=5; $x ^= 4;  // 101 ^ 100 = 001 (1) // xor
$x=5; $x <<= 1; // 101 << 1  =1010 (10)// left shift
$x=5; $x >>= 1; // 101 >> 1  =  10 (2) // right shift

$x = 0b101 & 0b100; // 0b100 (4)

// Additional logical operators
// Same as: $x = (true && false);
$x = true && false; // $x is false (0)

// Same as: ($x = true) and false;
$x = true and false; // $x is true (1)

$x = (true xor true); // false
```
# Chapter 04 - String
```php 
$a = 'Hello';

$b = $a . ' World'; // Hello World
$a .= ' World';     // Hello World

$c = 'World';
echo "Hello $c"; // "Hello World"
echo 'Hello $c'; // "Hello $c"

$s = <<<LABEL
Heredoc string (with parsing)
Goodbye
LABEL;

$name = 'John';
$s = <<<LABEL
Hello $name
LABEL;
echo $s; // "Hello John"

$s = <<<'LABEL'
Nowdoc string (without parsing)
LABEL;

$s = "Hello\nWorld";
echo "Hello<br>World";
$s = 'It\'s'; // "It's"

echo "\u{00C2A9}"; // © (copyright sign)
echo "\u{C2A9}";   // ©

$s = 'Hello';
$s[0] = 'J';
echo $s; // "Jello"

$s[strlen($s)-1] = 'y';
echo $s; // "Jelly"

$a = 'test';
$b = 'test';
$c = ($a === $b); // true
```

### String Functions
```php
$a = 'String';
```

### Search and replace characters in a string
```php
$b = str_replace('i', 'o', $a); // Strong
```

### Insert text at specified position
```php
$b = substr_replace($a, 'My ', 0, 0); // My String
```

### Get part of string specified by start and length
```php
$b = substr($a, 0, 3); // Str
```

### Convert to uppercase
```php
$b = strtoupper($a); // STRING
```

### Find position of the first occurance of a substring
```php
$i = strpos($a, 'i'); // 3 (starts at 0)
```

### Get string length
```php
$i = strlen($a); // 6
```

# Chapter 05 - Arrays

## Numeric arrays
```php
$a = array(1,2,3);
$a = [1,2,3];

$a[0] = 1;
$a[1] = 2;
$a[2] = 3;

$a[3] = 4;
$a[] = 5; // $a[4]

echo "$a[0] $a[1] $a[2] $a[3]"; // "1 2 3 4"
``` 

### Associative arrays
```php
$b = array('one' => 'a', 'two' => 'b', 'three' => 'c');

$b['one'] = 'a';
$b['two'] = 'b';
$b['three'] = 'c';

echo $b['one'] . $b['two'] . $b['three']; // "abc" 

$c = array(0 => 0, 1 => 1, 2 => 2);
$e = array(5 => 5, 6);
``` 

### Mixed arrays
```php
$d = array(0 => 1, 'foo' => 'bar');
echo $d[0] . $d['foo']; // "1bar"
```

### Multi-dimensional arrays
```php
$a = array(array('00', '01'), array('10', '11'));

$a[0][0] = '00';
$a[0][1] = '01';
$a[1][0] = '10';
$a[1][1] = '11';

echo $a[0][0] . $a[0][1] . $a[1][0] . $a[1][1];

$b = array('one' => array('00', '01'));
echo $b['one'][0] . $b['one'][1]; // "0001"

$c[][][][] = "0000"; // four dimensions
``` 

# Chapter 06 - Conditionals
### If statement
```php
$x = 1;
// ...
if ($x == 1) { 
  echo 'x is 1'; 
}
elseif ($x == 2) { 
  echo 'x is 2'; 
}
else { 
  echo 'x is something else'; 
}

if ($x == 1) 
  echo 'x is 1'; 
elseif ($x == 2) 
  echo 'x is 2';
else 
  echo 'x is something else';
```

### Switch statements
```php
switch ($x)
{
  case 1: echo 'x is 1'; break;
  case 2: echo 'x is 2'; break;
  default: echo 'x is something else';
}

if ($x == 1):     echo 'x is 1';  
elseif ($x == 2): echo 'x is 2';
else:             echo 'x is something else';
endif;

switch ($x):
  case 1:  echo 'x is 1'; break;
  case 2:  echo 'x is 2';  break;
  default: echo 'x is something else';
endswitch;
```

### Conditional embeed
```php
<?php if ($x == 1) { ?>
  This will show if $x is 1.
<?php } else { ?>
  Otherwise this will show.
<?php } ?>

<?php if ($x == 1): ?>
  This will show if $x is 1.
<?php else: ?>
  Otherwise this will show.
<?php endif; ?>
```

### Ternary operator expression
```php
$y = ($x == 1) ? 1 : 2;
```

### Ternary operator statement
```php
($x == 1) ? $y = 1 : $y = 2;
```

### Match expression
```php
$output = match($x) {
    1 => 'True',
    2 => 'False',
    default => 'Unknown'
};
echo $output;

match($x) {
  1 => $output = 'True',
  2 => $output = 'False',
  default => $output = 'Unknown'
};
echo $output;

$x = '1'; // string type
switch ($x)
{
  case 1: $output = 'integer'; break;
  case '1': $output = 'string';
}
echo $output; // "integer"

$output = match($x) {
  1 => 'integer',
  '1' => 'string',
};
echo $output; // "string"
```

# Chapter 07 - Loops

### While loop
```php
$i = 0;
while ($i < 10) { echo $i++; } // 0-9
```

### Do-while loop
```php
$i = 0;
do { echo $i++; } while ($i < 10); // 0-9
```

### For loop
```php
for ($i = 0; $i < 10; $i++) { echo $i; } // 0-9

$i = 0;
for (;$i < 10;) { echo $i++; }

for ($i = 0, $x = 9; $i < 10; $i++, $x--) {
  echo $x; // 9-0
}

$a = array(1,2,3);

for($i = 0; $i < sizeof($a); $i++) {
  echo $a[$i]; // "123"
}
```

### Foreach loop
```php
foreach ($a as $v) { 
  echo $v; // "123"
}

$a = array('one' => 1, 'two' => 2);

foreach ($a as $k => $v) {
  echo "$k = $v "; // "one = 1 two = 2 "
}
```

### Alternative syntax
```php
$i = 0;
while ($i < 10): echo $i++; endwhile;

for ($i = 0; $i < 10; $i++): echo $i; endfor;

$a = array(1,2,3);
foreach ($a as $v): echo $v; endforeach;
```

### Break
```php
for ($i = 0; $i < 5; $i++) 
{ 
  if ($i == 3) break; // end loop
  echo $i; // "012"
}

$i = 0;
while ($i++ < 10) 
{
  for (;;) { break 2; } // end for and while
}
```

### Continue
```php
for ($i = 0; $i < 5; $i++) 
{
  if ($i == 2) continue; // start next iteration
  echo $i; // "0134"
} 

$i = 0;
while ($i++ < 10) 
{
  for (;;) { continue 2; } // start next while iteration
}

$i = 0;
while ($i++ < 10) 
{
  switch ($i) 
  {
    case 1: continue 2; // start next while iteration
  }
}
```

### Goto
```php
goto myLabel; // jump to label
myLabel:      // label declaration

loop:
while ($finished === false)
{
  // 
  if ($try_again) goto loop; // restart loop
}
```

# Chapter 08 - Functions
```php
function myFunc() 
{ 
  echo 'Hello World'; 
}

myFunc(); // "Hello World"
``` 

### Function parameters
```php
function myFunc($x,$y) 
{ 
  echo $x . $y; 
}

myFunc('Hello', ' World'); // "Hello World"
``` 

### Optional parameters
```php 
function myFunc($x, $y = ' Earth') 
{ 
  echo $x . $y; 
} 
 
myFunc('Hello'); // "Hello Earth"
``` 

### Named arguments
```php 
function myNamed($a, $b = 2, $c = 4) 
{ 
  echo "$a $b $c";
}

myNamed(c: 3, a: 1); // "1 2 3"
myNamed(1, c: 3); // "1 2 3"
```
### Variable parameter list
```php 
function myArgs() 
{ 
  $x = func_get_arg(0);
  $y = func_get_arg(1);
  $z = func_get_arg(2);
  echo $x . $y . $z;
}  
 
myArgs('Fee', 'Fi', 'Fo'); // "FeeFiFo"
 
function myArgs2() 
{ 
  $num  = func_num_args();
  $args = func_get_args();
  for ($i = 0; $i < $num; $i++)
    echo $args[$i];
}
 
myArgs2('Fee', 'Fi', 'Fo'); // "FeeFiFo"

function myArgs3(...$args)
{ 
  foreach($args as $v) {
    echo $v;
  }
}
 
myArgs3(1, 2, 3); // "123"

$a = [1, 2, 3];
myArgs3(...$a); // "123"
```
### Return statement
```php 
function myFunc() 
{ 
  // Exit function and return value
  return 'Hello';
  echo 'Hi'; // never executes
} 

echo myFunc(); // "Hello"
 
function myNull() {}
 
if (myNull() === null)
  echo 'true'; // "true"
``` 

### Scope and lifetime
```php 
$x = 'Hello'; // global $x
 
function myFunc() 
{ 
  global $x;      // use global $x in this function
  $x .= ' World'; // change global $x
}
 
myFunc();
echo $x; // "Hello World"
 
function myFunc() 
{ 
  $GLOBALS['x'] .= ' World'; // change global $x
}
```
### Anonymous functions
```php 
$say = function($name)
{
  echo "Hello " . $name;
};
$say("World"); // "Hello World"

function myCaller($myCallback)
{
  echo $myCallback();
}
myCaller( function() { echo "Hello"; } ); // "Hello"

$a = [1, 2, 3];

$squared = array_map(function($val) 
{ 
  return $val * $val;
}, $a);

foreach ($squared as $v)
  echo $v; // "149"
```
### Closures
```php 
$x = 1, $y = 2;

$myClosure = function($z) use ($x, $y) 
{
  return $x + $y + $z;
};

echo $myClosure(3); // "6"
```
### Arrow functions
```php 
$x = 1, $y = 2;
$myClosure = fn($z) => $x + $y + $z;
echo $myClosure(3); // "6"
```
### Generators
```php
function getNum()
{
  for ($i = 0; $i < 5; $i++) {
    yield $i;
  }
}

foreach(getNum() as $v)
  echo $v; // "01234"

function countToFive() 
{
  yield 1;
  yield from [2, 3, 4];
  yield 5;
}

foreach (countToFive() as $v)
  echo $v; // 12345
```  
# Chapter 09 - Class
```php 
class MyRectangle
{
  public $x = 5, $y = 10;

  function newArea($a, $b) 
  { 
    return $a * $b; 
  }

  function getArea() 
  { 
    return $this->newArea($this->x, $this->y); 
  }

  function __construct($x, $y) 
  { 
    $this->x = $x; 
    $this->y = $y;
  }

  function __destruct() { echo "Destructed"; }
}

$r = new MyRectangle(5,10);
$r->x = 5; 
$r->y = 10;
$r->getArea(); // 50
unset($r); // "Destructed"
``` 
### Object comparison
```php
class Flag
{
  public $flag = true;
}

$a = new Flag();
$b = new Flag();

$c = ($a == $b);  // true (same values)
$d = ($a === $b); // false (different instances)
``` 
### Anonymous classes
```php 
$obj = new class {};

$o = new class('Hi') 
{
  public $x;
  public function __construct($a) 
  {
    $this->x = $a;
  }  
};

echo $o->x; // "Hi";
```
### Closure object
```php
class C { private $x = 'Hi'; }

$getC = function() { return $this->x; };
$getX = $getC->bindTo(new C, 'C');
echo $getX(); // "Hi"

// PHP 7+ code
$getX = function() { return $this->x; };
echo $getX->call(new C); // "Hi"
``` 
# Chapter 10 - Inheritance
```php 
// Parent class (base class)
class Rectangle
{
  public $x, $y;
  function __construct($a, $b) 
  { 
    $this->x = $a; 
    $this->y = $b; 
  }
}

// Child class (derived class)
class Square extends Rectangle
{
  function __construct($a) 
  { 
    parent::__construct($a,$a); 
  }
}

$s = new Square(5,10);
$s->x = 5; $s->y = 10;
$s = new Square(5);
``` 
### Final keyword
```php 
final class NotExtendable
{
  final function notOverridable() {}
}
```
### Instanceof operator
```php
$s = new Square(5);
$s instanceof Square;    // true
$s instanceof Rectangle; // true
```

# Chapter 11 - Access Levels
```php  
class MyClass
{
  public    $myPublic    = 'public';
  protected $myProtected = 'protected';
  private   $myPrivate   = 'private';

  function test()
  {
    echo $this->myPublic;    // allowed
    echo $this->myProtected; // allowed
    echo $this->myPrivate;   // allowed
  }  
}

class MyChild extends MyClass
{
  function test()
  {
    echo $this->myPublic;    // allowed
    echo $this->myProtected; // allowed
    echo $this->myPrivate;   // inaccessible	
  }  
}

$m = new MyClass();
echo $m->myPublic;    // allowed	
echo $m->myProtected; // inaccessible	
echo $m->myPrivate;   // inaccessible
``` 
### Var keyword
```php 
class MyVars
{
  var $x, $y; // deprecated property declaration
}
``` 
### Object access
```php 
class MyClass
{
  private $myPrivate;

  function setPrivate($obj, $val) {    
    $obj->myPrivate = $val; // set private property
  }
}
$a = new MyClass();
$b = new MyClass();
$a->setPrivate($b, 10);
``` 
### Accessors
```php
class Time
{
  private $minutes;

  function getMinutes() {
    return $this->minutes;
  }

  function setMinutes($val) {
    $this->minutes = $val;
  }
}

class Time
{
  private $seconds;

  function getMinutes() {
    return $this->seconds / 60;
  }

  function setMinutes($val) {
   if ($val > 0) { $this->seconds = $val * 60; }
   else { $this->seconds = 0; }
  }
}
```
# Chapter 12 - Static
```php
class MyCircle
{
  // Static/class members (only one copy)
  static $pi = 3.14; 

  // Instance members (one per object)
  public $r = 10;

  function getArea()
  { 
    return self::newArea($this->r); 
  }

  static function newArea($a) 
  {
    return self::$pi * $a * $a;
  }
}

echo MyCircle::$pi; // "3.14"
echo MyCircle::newArea(10); // "314"
``` 
### Static variables
```php
function add()
{
  static $val = 0;
  echo $val++;
}

add(); // "0"
add(); // "1"
add(); // "2"
``` 
### Late static bindings
```php
class MyParent
{
  protected static $val = 'parent';

  public static function getLateBindingVal()
  {
    return static::$val;
  }
}

class MyChild extends MyParent
{
  protected static $val = 'child';
}

echo MyChild::getLateBindingVal(); // "child"
``` 
# Chapter 13 - Constants
```php 
class MyCircle
{
  const PI = 3.14;
}

echo MyCircle::PI; // "3.14"

const PI = 3.14;
echo PI; // "3.14"

define('DEBUG', 1);
echo DEBUG; // "1"

define('ONE', 1);     // 1
define('TWO', ONE+1); // 2

define('DEBUG', 1, true);
echo debug; // "1"

if (!defined('PI')) 
  define('PI', 3.14); 

const CA = [1, 2, 3];    // PHP 5.6 or later
define('DA', [1, 2, 3]); // PHP 7 or later

// Const and define
const PI = 3.14;   // compile-time constant
define('E', 2.72); // run-time constant

// Magic constants
if(!isset($var))
{
  echo '$var not set on line ' . __LINE__;
}
```
# Chapter 14 - Interface
```php  
interface iMyInterface 
{
  public function myMethod();
  const PI = 3.14;
}

interface iComparable
{
  public function compare(iComparable $o);
}

class Circle implements iComparable
{
  public $r;
 
  public function compare(iComparable $o)
  {
    return $this->r - $o->r;
  }
}

function largest(iComparable $a, iComparable $b)
{
  return ($a->compare($b) > 0) ? $a : $b;
}
```  
# Chapter 15 - Abstract
```php 
abstract class Shape
{
  private $x = 100, $y = 100;
  abstract public function getArea();
}

class Rectangle extends Shape
{
  public function getArea() 
  { 
    return $this->x * $this->y; 
  }
}

class NonAbstract {}
abstract class MyAbstract extends NonAbstract {}

// Defines default functionality and definitions
abstract class Shape
{
  public $x = 100, $y = 100;
  abstract public function getArea();
}
// Class is a Shape 
class Rectangle extends Shape { /**/ }

// Defines a specific functionality
interface iComparable
{
  function compare(iComparable $o);
}
// Class can be compared
class MyClass implements iComparable { /**/ }
```  
# Chapter 16 - Traits
```php  
trait PrintFunctionality
{
  public function myPrint() { echo 'Hello'; }
}

class MyClass
{
  // Insert trait methods
  use PrintFunctionality;
}

$o = new MyClass();
$o->myPrint(); // "Hello"

class MyParent
{
  public function myPrint() { echo 'Base'; }
}

class MyChild extends MyParent 
{
  // Overrides inherited method
  use PrintFunctionality;

  // Overrides trait inserted method
  public function myPrint() { echo 'Child'; }
}

$o = new MyChild();
$o->myPrint(); // "Child"
``` 
# Chapter 17 - Importing Files
```php  
<?php
include 'myfile.php';
require 'myfile.php'; // halt on error
include_once 'myfile.php'; // include only once
require_once 'myfile.php'; // require only once
?>
```  
```php 
// Auto load
function __autoload($class_name)
{
  include $class_name . '.php';
}

// Attempt to auto include MyClass.php
$obj = new MyClass();
``` 
# Chapter 18 - Type Declarations
```php 
function myPrint(array $a) 
{
  foreach ($a as $v) { echo $v; }
}

myPrint( array(1,2,3) ); // "123"
myPrint('Test'); // error

function myCall(callable $callback, $data) 
{
  $callback($data);
}

$say = function($s) { echo $s; };
myCall( $say, 'Hi' ); // "Hi";

class MyClass {
  function myCallback($s) {
    echo $s;
  }
}

$o = new MyClass();
myCall( array($o, 'myCallback'), 'Hi' ); // "Hi"

function isTrue(bool $b) 
{
  return ($b === true);
}

echo isTrue(true);  // "1"
echo isTrue(false); // ""

// Return type declarations
function f(): array {
  return [];
}

interface I {
  static function myArray(array $a): array;
}

class C implements I {
  static function myArray(array $a): array {
    return $a;
  }
}

function myFunc(): void {
  return; // empty return statement
}

class MyTest 
{
  public function getNewObject(): static 
  {
    return new MyTest();
  }
}

// Strict typing
declare(strict_types=1);

function showString(string $s) {
  echo $s;
}

showString(5); // Fatal error: Uncaught TypeError

// Nullable types
function nullOrInt(?int $i)
{
  echo $i === null ? 'null' : 'int';
}

echo nullOrInt(3); // "int"
echo nullOrInt(null); // "null"

// Union types
function squared(int|float $i): int|float
{
  return $i ** 2;
}

echo squared(2); // "4"
echo squared(1.5); // "2.25"

function trueOrNull(true|null $j): true|null
{
  return $j === null ? true : null;
}

// Property type declarations
class MyClass 
{
  public int $a = 3;
}

$o = new MyClass;
$o->a = 5; // allowed
$o->a = 'string'; // fatal error: TypeError

class MyType
{
  public int $a; // uninitialized
  public $b; // null
}

$t1 = new MyType;
$o->t1 = 5;
$i = $o->t1; // ok 

$t2 = new MyType;
$i = $o->t2; // error
``` 
# Chapter 19 - Type Conversions
```php  
$myBool = false;
$myInt = (int)$myBool; // 0

echo $myBool;      // ""
echo (int)$myBool; // "0"

$myInt = 10;
$myArr = (array)$myInt;
$myArr = array($myInt); // same as above
echo $myArr[0]; // "10"

$myObj = (object)$myInt;
echo $myObj->scalar; // "10"

$myNull = (unset)$myInt;
$myNull = null; // same as above

$myVar = 1.2;
settype($myVar, 'int'); // convert variable to int

$myVar = 1.2;
$myVar = (int)$myVar; // 1

$myBool = true;
echo gettype($myBool); // "boolean"
``` 
# Chapter 20 - Variable Testing
```php  
// Isset
isset($a); // false

$a = 10;
isset($a); // true

$a = null;
isset($a); // false

// Empty
empty($b); // true

$b = false;
empty($b); // true

// Is_null
$c = null;
is_null($c); // true

$c = 10;
is_null($c); // false
is_null($d); // true (undefined variable notice)

$c = null;
$c === null; // true

// Unset
$e = 10;
unset($e); // delete $e

$o = 5; // global variable
function myUnset() 
{
  // Make $o a reference to $GLOBALS['o']
  global $o;

  // Remove the reference variable
  unset($o);

  // Remove the global variable
  unset($GLOBALS['o']);
}

$var = null; // free memory
unset($var); // delete variable

// Null coalescing operator
$x = null;
$name = $x ?? 'unknown'; // "unknown"
$name = isset($x) ? $x : 'unknown';

// Assign value if $name is unassigned
$name ??= 'unknown';

// Same as above
if(!isset($name)) { $name = 'unknown'; }

// Functionally same as above
$name = $name ?? 'unknown';

// Nullsafe operator
$result = $obj?->myMethod();

// Determining types
is_numeric(10.5);   // true  (float)
is_numeric('33');   // true  (numeric string)
is_numeric('text'); // false (non-numeric string)

// Variable information
$a = array('one', 'two', 'three'); 
print_r($a);

eval('$b = ' . var_export($a, true) . ';');
``` 
# Chapter 21 - Overloading
```php  
// Property overloading
class MyProperties
{
  private $data = array();

  public function __set($name, $value)
  {
    $this->data[$name] = $value;
  }

  public function __get($name)
  {
    if (array_key_exists($name, $this->data))
      return $this->data[$name]; 
  }
}

$obj = new MyProperties();

$obj->a = 1;  // __set called
echo $obj->a; // __get called
 
// Method overloading
class MyClass
{
  public function __call($name, $args)
  {
    echo "Calling $name $args[0]";
  }

  public static function __callStatic($name, $args)
  {
    echo "Calling $name $args[0]";
  }
}

// "Calling myTest in object context"
(new MyClass())->myTest('in object context');

// "Calling myTest in static context"
MyClass::myTest('in static context');
 
// Isset and unset overloading
class MyClass
{
  private $data = array();

  public function __set($name, $value) {
    $this->data[$name] = $value;
  }
  public function __get($name) {
    if (array_key_exists($name, $this->data))
      return $this->data[$name];
  }

  public function __isset($name) {
    return isset($this->data[$name]);
  }

  public function __unset($name) {
    unset( $this->data[$name] );
  }
}

$obj = new MyClass();
$obj->name = "Joe";

isset($obj->name); // true
isset($obj->age);  // false

unset($obj->name); // delete property
isset($obj->name); // false

empty($obj->name); // false
empty($obj->age);  // true
```
# Chapter 22 - Magic Methods
```php  
// Tostring
class MyClass
{
  public function __toString()
  {
    return 'Instance of ' . __CLASS__;
  }
}

$obj = new MyClass();
echo $obj; // "Instance of MyClass"
 
// Invoke
class MyClass
{
  public function __invoke($arg)
  {
    echo $arg;
  }
}

$obj = new MyClass();
$obj('Test'); // "Test"
 
// Object serialization
class MyConnection
{
  public $link, $server, $user, $pass;

  public function connect()
  {
    $this->link = mysql_connect($this->server, 
                                $this->user, 
                                $this->pass);
  }

  public function __sleep()
  {
    return array('server', 'user', 'pass');
  }

  public function __wakeup()
  {
    if(isset($server, $user, $pass))
      $this->connect();
  }
}

$obj = new MyConnection();
// 

$bin = serialize($obj);   // serialize object
$obj = unserialize($bin); // restore object
 
// Set state
class Fruit
{ 
  public $name = 'Lemon';

  static function __set_state(array $myarray) 
  {
    $tmp = new Fruit();
    $tmp->name = $myarray['name'];
    return $tmp; 
  }
}

$export = var_export(new Fruit(), true);
eval('$MyFruit = ' . $export . ';');

// Object cloning
class Fruit {}

$f1 = new Fruit();
$f2 = $f1;       // copy object reference
$f3 = clone $f1; // copy object

class Apple {}

class FruitBasket 
{
  public $apple;

  function __construct() { $apple = new Apple(); }

  function __clone()
  {
    $this->apple = clone $this->apple;
  }
}
``` 
# Chapter 23 - User Input
```php  
<?php // myform.php ?>
<!doctype html>
<html>
<body>
  <form action="mypage.php" method="post">
    <input type="text" name="myString">
    <input type="submit">
  </form>
</body>
</html>

<?php // sender.php ?>
<!doctype html>
<html>
<body>
  <a href="receiver.php?myString=Foo+Bar">link</a>
</body>
</html>

<?php // receiver.php ?>
<!doctype html>
<html>
<body>
  <?php echo $_GET['myString']; // "Foo Bar" ?>
</body>
</html>
```
```php 
echo $_POST['myString'];
echo $_GET['myString'];
echo $_REQUEST['myString'];

// Security concerns
if(!filter_var($_POST['email'], FILTER_VALIDATE_EMAIL))
  echo "Invalid email address";

// Sanitize for database use
$name = mysql_real_escape_string($_POST['name']);

// Execute SQL command
$sql = "SELECT * FROM users WHERE user='" . $name . "'";
$result = mysql_query($sql);

// Sanitize for web page use
echo htmlspecialchars($_POST['comment']);

// Submitting arrays
<input type="text" name="myArr[]" />
<input type="text" name="myArr[]" />

<input type="text" name="myArr[name]" />

$val1 = $_POST['myArr'][0];
$val2 = $_POST['myArr'][1];
$name = $_POST['myArr']['name'];

<select name="myArr[]" size="3" multiple="true">
  <option value="apple">Apple</option>
  <option value="orange">Orange</option>
  <option value="pear">Pear</option>
</select>

foreach ($_POST['myArr'] as $item)
  echo $item . ' '; // ex "apple orange pear"
 
// File uploading
<form action="mypage.php" method="post"
      enctype="multipart/form-data">
  <input name="myfile" type="file">
  <input type="submit" value="Upload">
</form> 
 
$dest = 'upload/' . basename($_FILES['myfile']['name']);
$file = $_FILES['myfile']['tmp_name'];
$err  = $_FILES['myfile']['error'];

if($err == 0 && move_uploaded_file($file, $dest))
  echo 'File successfully uploaded';

phpinfo(); // display PHP information
```
# Chapter 24 - Cookies
```php  
setcookie("lastvisit", date("H:i:s"), time() + 60*60);

setcookie("lastvisit", 
           date("H:i:s"), 
           time() + 60*60,
           '/foo/',
           'fr.example.com');

if (isset($_COOKIE['lastvisit']))
  echo "Last visit: " . $_COOKIE['lastvisit'];

// Delete cookie
setcookie("lastvisit", 0, 0);
```

# Chapter 25 - Sessions

```php  
session_start();

if(isset($_SESSION['views']))
  $_SESSION['views'] += 1;
else
  $_SESSION['views'] = 1;

echo 'Views: ' . $_SESSION['views'];

// Deleting a session
unset($_SESSION['views']); // destroy session variable
session_destroy(); // destroy session
``` 
# Chapter 26 - Namespaces
```php 
namespace my;

// Belongs to my namespace
class MyClass {}

<?php
namespace my;
class MyClass {}
?>
<html><body></body></html>
```
```php  
// Nested namespaces
namespace my\sub;
class MyClass {} // my\sub\MyClass

// Alternative syntax
<?php
namespace my
{
  class MyClass {}
?>
<html><body></body></html>
<?php }?>
```
```php  
// Namespaced code
namespace my
{
  const PI = 3.14;
}

// Global code
namespace
{
  echo my\PI; // "3.14"
}

// Referencing namespaces
namespace my
{
  class MyClass {}
}

namespace other
{
  // Fully qualified name
  $obj = new \my\MyClass();
}
 
namespace my
{
  class MyClass {}
}

namespace
{
  // Qualified name
  $obj = new my\MyClass();
}
 
namespace my
{
  class MyClass {}

  // Unqualified name
  $obj = new MyClass();
}

namespace
{
  function myPrint() { echo 'global'; }
}

namespace my
{
  // Falls back to global namespace
  myPrint(); // "global"
}
 
namespace my
{
  function myPrint() { echo 'my'; }

  // Call function from global namespace
  \myPrint(); // "global"
  myPrint();  // "my"
}

// Namespace aliases
namespace my;
class MyClass {}

namespace foo;
use my\MyClass as MyAlias;
$obj = new MyAlias();
 
namespace foo;
use my\MyClass as MyAlias;
{
  $obj = new MyAlias();
}
 
namespace foo;
use \my\MyClass; // same as my\MyClass as MyClass
$obj = new MyClass();
 
namespace foo;
use my\Class1 as C1, my\Class2 as C2;
use my\{ Class1 as C1, Class2 as C2 };

namespace my\space {
  const C = 5;
  function f() {}
}

namespace {
  use const my\space\C;
  use function my\space\f;
}
 
// Namespace keyword
namespace my\name
{
  function myPrint() { echo 'Hi'; }
}
namespace my
{
  namespace\name\myPrint(); // "Hi"
  name\myPrint();           // same as above
}
``` 
# Chapter 27 - References
```php 
// Assign by reference
$x = 5;
$r = &$x; // r is a reference to x
$s =& $x; // alternative syntax

$r = 10; // assign value to $r/$x
echo $x; // "10"

// Pass by reference
function myFunc(&$x) { $x .= ' World'; }

$x = 'Hello';
myFunc($x); // reference to x is passed
echo $x;    // "Hello World"

class MyClass { public $x = 1; }

function modifyVal($o)
{
  $o->x = 5;
  $o = new MyClass(); // new local object
}

$o = new MyClass();
modifyVal($o); // pointer to object is passed
echo $o->x; // "5"

class MyClass { public $x = 1; }

function modifyRef(&$o)
{
  $o->x = 5;
  $o = new MyClass(); // new object
}

$o = new MyClass();
modifyRef($o); // reference to object is passed
echo $o->x; // "1"

// Return by reference
class MyClass
{
  public $val = 10;

  function &getVal()
  {
    return $this->val;
  }
}

$obj = new MyClass();
$myVal = &$obj->getVal();
``` 
# Chapter 28 - Advanced Variables
```php  
// Curly syntax
$fruit = 'Apple';
echo "Two {$fruit}s"; // "Two Apples"

for ($i = 1; $i <= 3; $i++)
  ${'x'.$i} = $i;

echo "$x1 $x2 $x3"; // "1 2 3"

for ($i = 'a'; $i <= 'c'; $i++)
  $$i = $i;

echo "$a $b $c"; // "a b c"
 
// Variable variable names
$a = 'foo';
$$a = 'bar';

echo $foo; // "bar"
echo $$a;  // "bar"
 
$arr = array('a' => 'Foo', 'b' => 'Bar');

foreach ($arr as $key => $value)
{
  $$key = $value;
}

echo "$a $b"; // "Foo Bar"
 
// Variable function names
function myPrint($s) { echo $s; }

$func = 'myPrint';
$func('Hello'); // "Hello"
 
// Variable class names
class MyClass {}

$classname = 'MyClass';
$obj = new $classname();
 
// Variable class member names
class MyClass
{
  public $myProperty = 10;
}

$obj = new MyClass();
echo $obj->{'myProperty'}; // "10"
 
# Chapter 29 - Error Handling
 
if (is_readable('myfile.txt'))
  $handle = fopen('myfile.txt', 'r');
 
$handle = @fopen('myfile.txt', 'r');

if ($handle === false) 
{
  echo 'File not found.';
}
else 
{
  // Read the content of the whole file 
  $content = fread($handle, filesize('myfile.txt'));

  // Close the file handler
  fclose($handle);
}
 
// E_NOTICE (<PHP8)  Use of undefined variable
$a = $x;

// E_WARNING  Missing file
$b = fopen('missing.txt', 'r');

// E_ERROR  Missing function
$c = missing();
 
// Error handling environment
error_reporting(E_ALL | ~E_NOTICE); // all but E_NOTICE

// During development
error_reporting(E_ALL | E_STRICT);

// During production
ini_set('display_errors','0');

// During development
ini_set('log_errors','1');
 
// Custom error handlers
set_error_handler('myError', E_ALL | E_STRICT);

function myError($errlvl, $errdesc, $errfile, $errline)
{
  switch($errlvl)
  {
    case E_USER_ERROR:
      error_log("Error: $errdesc", 1, 'me@example.com');
      require_once('my_error_page.php');
      return true;
  }
  return false;
}
 
// Raising errors
if( !isset($myVar) )
  trigger_error('$myVar not set'); // E_USER_NOTICE
```  

# Chapter 30 - Exception Handling

```php  

function invert($x)
{
  if ($x == 0) {
    throw new LogicException('Division by zero');
  }
  return 1 / $x;
}

try
{
  $div = invert(0);
}
catch (LogicException $e) 
{
  echo $e->getMessage(); // "Division by zero"
}
 
// Finally block
$resource = myopen();
try { myuse($resource); }
catch(Exception $e) {}
finally { myfree($resource); }
 
// Re-throwing exceptions
try { $div = invert(0); } 
catch (LogicException $e) { throw $e; }
 
$name = $_GET['name'] ?? throw new Exception('name missing');

// Uncaught exception handler
set_exception_handler('myException');

function myException($e)
{
  $file = 'exceptionlog.txt';
  file_put_contents($file, $e->getMessage(), FILE_APPEND);
  require_once('my_error_page.php');
  exit;
}
```

# Chapter 31 - Assertions

```php
// Make sure $myVar is set
assert(isset($myVar));

assert(isset($myVar), '$myVar not set');

assert(false, new AssertionError('Assert failed'));

// Assert performance
assert_options(ASSERT_ACTIVE, 0); // disable assertions

assert('isset($myVar)');
```