<h1>JavaScript</h1>

This document aims to highlight the basic of Javascript. <br>
References: [Free Code Camp](https://www.youtube.com/watch?v=PkZNo7MFNFg)

<h2>Data-type and variables</h2>

Seven different data types.
1. undefined
2. null
3. boolean
4. string
5. symbol
6. number
7. object

Three ways to declare variables.

<h3> 1) Using var keyword</h3>

var can be use throughout the program.
```javascript
var myName = "Boo"; //String variable
var myNumber = 100; //number variable
var decimalNum = 6.993 //floating point number
```
<h3> 2) Using let keyword</h3>

let will only be used within the scope where we declare.
```javascript
let ourName = "bandName";
```

<h3> 3) Using const keyword</h3>

const cannot be change.
```javascript
const pi = 3.14;
```

<br>

<h2>Console log</h2>

Allow you to print onto the console.

```javascript
console.log("Hello World");

var a = 10;
console.log(a);
```

<br>

<h2>Operations</h2>

Performing operations is the same as in other programming language.

<h3>Basic operations</h3>

```javascript
var a = 5;
var b = 10;

var sum = a + b;
var diff = a - b;
var mul = a * b;
var div = a / b;
var remainder = a % b;
```

<h3>Increment and Decrement</h3>

```javascript
var a = 10;

var increment = a++;
var decrement = a--;
```

<h3>Compound Assignment with Augmented Operations</h3>

```javascript
var a = 10;
var b = 5;
var c = 4;
var d = 15

a += 12; // a = a + 12
b -= 10; // b = b - 10 
c *= 11; // c = c * 11
d /= 3; // d = d / 3
```

<br>

<h2>Strings</h2>

<h3>String Declaration</h3>

* String can be declared using " ".
```javascript
var myString = "This is a String";
```

<h3>Escape Character</h3>

* Everything inside " " is a String, it denotes end and start of a String.
* What if I want to use " " inside a String?
* Solution: Add \ before each " inside " ".
```javascript
var myString = "Adding \"double quote\" inside a String."
```

* Below is a detailed output list using escape char.

|Code |Output         |
|-----|---------------|
|\\'  |Single quote   |
|\\"  |Double quote   |
|\\\  |Backslash      |
|\\n  |New line       |
|\\r  |carriage return|
|\\t  |tab            |
|\\b  |Backspace      |
|\\f  |Form feed      |


<h3>Quoting without " \ " character</h3>

* To use " " in a string without the escape character, we can simply use single quote to start and end the string.
* Double or single quote are both allowed in Javascript.
* To use both single and double quote in a string, we can use \` ` to start and end the string.
```javascript
var myStr = 'This is a "String" with quote.'
var myStr = `'This is a "String" with quote.'`
```

<h3>String Concatenation</h3>

* String can be concatenate using the "+" operator.

```javascript
var ConcatStr = "This comes first. " + "This comes second."
ConcatStr += " Another additional string."
```

<h3>Constructing Strings with Variables</h3>

```javascript
var myStr = "This is a string too."
var Str = "This is a string. " + myStr;
```

<h3>Finding Length of String</h3>

```javascript
var strLen = 0;
var myStr = "Hello World";

strLen = myStr.length;
```

<h3>Bracket Notation</h3>

* We can find any char in a string using bracket notation.
* Javascript uses 0-based indexing as well.

```javascript
var myStr = "HelloWorld";
var firstChar = myStr[0];

var lastChar = myStr[myStr.length-1];
```

<h3>String Immutability</h3>

* String are immutable, i.e. cannot be alter once created.
* Still, they can be change.

```javascript
var myStr = "Jello World";
myStr[0] = "H"; //This will give an error

myStr = "Hello World" //Must do this

```