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

<h4> 1) Using var keyword</h4>

var can be use throughout the program.
```javascript
var myName = "Boo"; //String variable
var myNumber = 100; //number variable
var decimalNum = 6.993 //floating point number
```
<h4> 2) Using let keyword</h4>

let will only be used within the scope where we declare.
```javascript
let ourName = "bandName";
```

<h4> 3) Using const keyword</h4>

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

<h4>Basic operations</h4>

```javascript
var a = 5;
var b = 10;

var sum = a + b;
var diff = a - b;
var mul = a * b;
var div = a / b;
var remainder = a % b;
```

<h4>Increment and Decrement</h4>

```javascript
var a = 10;

var increment = a++;
var decrement = a--;
```

<h4>Compound Assignment with Augmented Operations</h4>

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

<h4>String Declaration</h4>

* String can be declared using " ".
```javascript
var myString = "This is a String";
```
<br>

<h4>Escape Character</h4>

* Everything inside " " is a String, it denotes end and start of a String.
* What if I want to use " " inside a String?
* Solution: Add \ before each " inside " ".
```javascript
var myString = "Adding \"double quote\" inside a String."
```

