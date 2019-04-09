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

<h4>Escape Character</h4>

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


<h4>Quoting without " \ " character</h4>

* To use " " in a string without the escape character, we can simply use single quote to start and end the string.
* Double or single quote are both allowed in Javascript.
* To use both single and double quote in a string, we can use \` ` to start and end the string.
```javascript
var myStr = 'This is a "String" with quote.'
var myStr = `'This is a "String" with quote.'`
```

<h4>String Concatenation</h4>

* String can be concatenate using the "+" operator.

```javascript
var ConcatStr = "This comes first. " + "This comes second."
ConcatStr += " Another additional string."
```

<h4>Constructing Strings with Variables</h4>

```javascript
var myStr = "This is a string too."
var Str = "This is a string. " + myStr;
```

<h4>Finding Length of String</h4>

```javascript
var strLen = 0;
var myStr = "Hello World";

strLen = myStr.length;
```

<h4>Bracket Notation</h4>

* We can find any char in a string using bracket notation.
* Javascript uses 0-based indexing as well.

```javascript
var myStr = "HelloWorld";
var firstChar = myStr[0];

var lastChar = myStr[myStr.length-1];
```

<h4>String Immutability</h4>

* String are immutable, i.e. cannot be alter once created.
* Still, they can be change.

```javascript
var myStr = "Jello World";
myStr[0] = "H"; //This will give an error

myStr = "Hello World" //Must do this
```

<br>

<h2>Arrays</h2>

<H4>Using Array to Store Variables</h4>

* Elements inside an array is separated by a comma. 

```javascript
var arr = ["John", 23]; //first element is a string, 2nd is a number.
var aar2 = ["One", 1, "Two", 2];
```

<h4>Nested Array</h4>

```javascript
var arr = [["Universe", 42], ["Everything", 101010]];
//An array containing 2 arrays
```

<h4>Getting an Element from an array</h4>

```javascript
var dataArray = [50, 60, 70, 80];
var fifty = dataArray[0];
```

<h4>Modifying Array Data with Indexes</h4>

* Unlike string, we can modify data with indexes.

```javascript
var arr = [50, 60, 70, 80];
arr[2] = 75;
```

<h4>Access Multi-Dimensional Arrays with Indexes</h4>

```javascript
var arr = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];

var myData = arr[0][0]; //1
var myData2 = arr[3][0][0]; //10
```

<h4>Manipulate Arrays with push()</h4>

* Use to append data to an array.

```javascript
var arr = ["Stimpson", "J", "Dog"];
arr.push(["happy", "joy"]);
//array now equals to ["Stimpson, "J", "Dog", ["happy, "joy"]];
```

<h4>Manipulate Arrays with pop()</h4>

* Use to remove last element from an array.

```javascript
var arr = [1,2,3];
arr.pop();
//arr now equals [1,2]
```

<h4>Manipulate Arrays with shift()</h4>

* Similar to pop(), but...
* Remove 1st element instead of last.

```javascript
var arr = [1,2,3];
arr.shift();
//arr now equals [2,3]
```

<h4>Manipulate Arrays with unshift()</h4>

* Similar to push() but...
* Add element to first element instead of last.

```javascript
var arr = [1,2,3];
arr.unshift(0);
//arr now equals [0,1,2,3]
```

<br>

<h2>Functions</h2>

* Functions can be created just like other language.

```javascript
var a = 5;
var b = 10;
var sum = Addition(a, b);

function Addition(a, b) {
  console.log(a + b);
}
```

<h4>Function Scope</h4>

* Function can be declared without the "var" keyword, this will make the variable global.
* If a variable is declared with a var keyword inside a function, that variable is only available in that function.
* Global variable is created outside of a function.

```javascript
var myGlobal = 10;

function funct1(){
  anotherGlobal = 20; //no var keyword, global
  var funct1Var = 10; //scope on in this function.
}

function  funct2() {
  var output = "";
  if(typeof myGlobal != "undefined"){
    output += "Globa; variable: " + myGlobal;
  }
  if(typeof anotherGlobal != "undefined"){
    output += "anotherGlobal: " + anotherGlobal;
  }
}
```

<h4>Global vs. Local Scope in Functions</h4>

* It is possible to have a local and global variable with the same name.
* The local variable will take precedence over the global variable.

```javascript
var outerWear = "T-Shirt"; //global variable

function myOutfit() {
  var outerWear = "Sweater"; //local variable
  return outerWear
}

console.log(myOutfit()); //sweater
console.log(outerWear); //T-Shirt
```

<h4>Understanding Undefined Value Returned from a Function</h4>

* Function can return value, but can choose not to as well.

```javascript
var sum = 0;
function add(){
  sum += 3;
}

function addFive(){
  sum += 5;
}

console.log(add()); //undefined since no return value
```

<h4>Queue</h4>

* Understanding how queue works.
* push() adds an item to the end of the queue.
* shift() remove the first element of the queue.

```javascript
function nextInLine(arr, item) {
  arr.push(item); //add item to the rear of arr
  return arr.shift(); //remove first element of arr
}

var testArr = [1,2,3,4,5];

console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

<br>
<br>

<h2>Boolean Values</h2>

* True or False only.

<h4>Check equal</h4>

* Want to check if 2 values are the same.
* Like in other programming language, use ==.

```javascript
function equate(val){
  if(val == 12){
    return "Equal";
  }
  return "Not Equal";
}

equate(10);
```

<h4>Strict equality Operator</h4>

* == will convert both comparable to the same type.
* 3 == '3' will equate to true.
* === does not do any conversion.
* 3 === 3 is **true**, 3 === '3' is **false**

<h4>Inequality, Strict Inequality and Logical Comparing Operator</h4>

|Code|Description      |
|----|-----------------|
|!=  |Not equal, convert so both data type are the same.|
|!== |Strict inequality, does not convert both data type|
|\>  |More than         |
|>=  |More than or equal|
|<   |Less than         |
|<=  |Less than or equal|
